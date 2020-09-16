<template>
  <div>
    <druxt-menu component="ul" name="main">
      <template #item="{ item: { entity }, to }">
        <li>
          <nuxt-link :to="to">{{ entity.attributes.title }}</nuxt-link>
        </li>
      </template>

      <template #parent="{ item: { entity, children }, to }">
        <li>
          <nuxt-link :to="to">{{ entity.attributes.title }}</nuxt-link>
          <ul>
            <druxt-menu-item
              v-for="item in children"
              :key="item.entity.id"
              :item="item"
            />
          </ul>
        </li>
      </template>
    </druxt-menu>
  </div>
</template>
