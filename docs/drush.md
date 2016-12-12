# Drush Commands

## Clearing cache

Standard cache-rebuild

    drush cr

Using mysql -> select database -> truncate following cache tables

    TRUNCATE cache_config;
    TRUNCATE cache_container;
    TRUNCATE cache_data;
    TRUNCATE cache_default;
    TRUNCATE cache_discovery;
    TRUNCATE cache_dynamic_page_cache;
    TRUNCATE cache_entity;
    TRUNCATE cache_menu;
    TRUNCATE cache_render;
    TRUNCATE cache_toolbar
