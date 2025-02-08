---
title: Blogs
summary: My courses
type: landing

cascade:
  - _target:
      kind: page
    params:
      show_breadcrumb: true

sections:
  - block: collection
    id: blogs
    content:
      title: Blogs
      filters:
        folders:
          - blogs
    design:
      view: article-grid
      columns: 2
  - block: collection
    id: math285
    content:
      title: Math285
      filters:
        folders:
          - blogs/Math285
    design:
      view: article-grid
      columns: 2
---
