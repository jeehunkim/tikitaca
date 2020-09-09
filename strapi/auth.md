# contentAuth

## /api/xxx/controllers/xxx.js

각 게시글의 주인만 수정/삭제되도록 권한추가 

```javascript
'use strict';
module.exports = {};
```

Add Create

{% code title="" %}
```javascript
async create(ctx) {
        let entity;
        if (ctx.is('multipart')) {
            const { data, files } = parseMultipartData(ctx);
            data.author = ctx.state.user.id;
            entity = await strapi.services.article.create(data, { files });
        } else {
            ctx.request.body.author = ctx.state.user.id;
            entity = await strapi.services.article.create(ctx.request.body);
        }
        return sanitizeEntity(entity, { model: strapi.models.article });
    },
```
{% endcode %}

Add update

```javascript
async update(ctx) {
        const { id } = ctx.params;
    
        let entity;
    
        const [article] = await strapi.services.article.find({
            id: ctx.params.id,
            'author.id': ctx.state.user.id,
        });

        if (!article) {
            return ctx.unauthorized(`You can't update this entry`);
        }
    
        if (ctx.is('multipart')) {
            const { data, files } = parseMultipartData(ctx);
            entity = await strapi.services.article.update({ id }, data, {
                files,
            });
        } else {
            entity = await strapi.services.article.update({ id }, ctx.request.body);
        }
    
        return sanitizeEntity(entity, { model: strapi.models.article });
    },
```

Add Delete

```javascript
async delete(ctx) {
        const { id } = ctx.params;
    
        let entity;
    
        const [article] = await strapi.services.article.find({
            id: ctx.params.id,
            'author.id': ctx.state.user.id,
        });
 
        if (!article) {
            return ctx.unauthorized(`You can't delete this entry`);
        }
 
        let entity = await strapi.services.article.delete({ id: ctx.params.id });
        return sanitizeEntity(entity, { model: strapi.models.article});
    },
```

final exam

```javascript
'use strict';

const { parseMultipartData, sanitizeEntity } = require("strapi-utils");

/**
 * Read the documentation (https://strapi.io/documentation/v3.x/concepts/controllers.html#core-controllers)
 * to customize this controller
 */

module.exports = {
  /**
   * Create a new Category
   *
   * @param {*} ctx The Strapi Context
   */
  async create(ctx) {
    let entity;

    if (ctx.is("multipart")) {
      const { data, files } = parseMultipartData(ctx);
      data.user = ctx.state.user.id;
      entity = await strapi.services.category.create(data, { files });
    } else {
      ctx.request.body.user = ctx.state.user.id;
      entity = await strapi.services.category.create(ctx.request.body);
    }
    return sanitizeEntity(entity, { model: strapi.models.category });
  },

  /**
   * Update a category
   *
   * @param {*} ctx the request context
   */

  async update(ctx) {
    const { id } = ctx.params;

    let entity;

    // Find the category matching the ID and the user
    const [category] = await strapi.services.category.find({
      id: ctx.params.id,
      "user.id": ctx.state.user.id,
    });

    if (!category) {
      return ctx.unauthorized(`You can't update this entry`);
    }

    // Update the category
    if (ctx.is("multipart")) {
      const { data, files } = parseMultipartData(ctx);
      entity = await strapi.services.category.update({ id }, data, {
        files,
      });
    } else {
      entity = await strapi.services.category.update({ id }, ctx.request.body);
    }

    return sanitizeEntity(entity, { model: strapi.models.category });
  },

  /**
   * List all the categories beloinging to the requesting user
   *
   * @param {*} ctx the request context
   */

  async find(ctx) {
    let entities;

    if (ctx.query._q) {
      entities = await strapi.services.category.search({
        ...ctx.query,
        "user.id": ctx.state.user.id,
      });
    } else {
      entities = await strapi.services.category.find({
        ...ctx.query,
        "user.id": ctx.state.user.id,
      });
    }

    return entities.map((entity) =>
      sanitizeEntity(entity, { model: strapi.models.category })
    );
  },

  /**
   * Get the category with a specific ID
   *
   * @param {*} ctx the request context
   */
  async findOne(ctx) {
    const { id } = ctx.params;

    const entity = await strapi.services.category.findOne({
      id,
      "user.id": ctx.state.user.id,
    });

    if (!entity) {
      return ctx.unauthorized(`You can't view this entry`);
    }

    return sanitizeEntity(entity, { model: strapi.models.category });
  },

  /**
   * Count of the categories of the requesting user
   *
   * @param {*} ctx the request context
   */

  count(ctx) {
    if (ctx.query._q) {
      return strapi.services.category.countSearch({
        ...ctx.query,
        "user.id": ctx.state.user.id,
      });
    }
    return strapi.services.category.count({
      ...ctx.query,
      "user.id": ctx.state.user.id,
    });
  },

  /**
   * Delete a record
   *
   * @param {*} ctx the request context
   */
  async delete(ctx) {
    const [category] = await strapi.services.category.find({
      id: ctx.params.id,
      "user.id": ctx.state.user.id,
    });

    if (!category) {
      return ctx.unauthorized(`You can't delete this entry`);
    }

    let entity = await strapi.services.category.delete({ id: ctx.params.id });
    return sanitizeEntity(entity, { model: strapi.models.category });
  },
};
```

