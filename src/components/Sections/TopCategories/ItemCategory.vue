<template>
  <div class="item-category">
    <div class="item-category__wrapper">
      <Icon
              :name="data.icon"
              :width="32"
              :height="32"
      />
      <div class="item-category__title">{{data.title}}</div>
    </div>
  </div>
</template>

<script>
  import Icon from 'components/Icon'

  export default {
    name: 'ItemCategory',
    components: {
      Icon,
    },
    props: {
      data: Object,
    },
  }
</script>

<style lang="scss">
  .item-category {
    margin: 8px 0;
    padding: 15px;
    display: inline-block;
    border-color: #ddd;
    opacity: 1;
    border-radius: 2px;
    width: 100%;
    cursor: pointer;
    position: relative;
  }

  .item-category__wrapper {
    display: flex;
    flex-direction: row;
    border-color: #ddd;
  }

  .item-category:before,
  .item-category:after {
    content: '';
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    transition: 0.2s ease;
    pointer-events: none;
  }

  .item-category:before {
    box-shadow: 0 0 1px 1px rgba(20, 23, 28, 0.1), 0 3px 1px 0 rgba(20, 23, 28, 0.1);
    opacity: 1;
  }

  .item-category:hover:before {
    opacity: 0;
  }

  .item-category:after {
    box-shadow: 0 2px 8px 2px rgba(20, 23, 28, 0.15);
    opacity: 0;
  }

  .item-category:hover:after {
    opacity: 1;
  }

  .item-category__icon {
    font-size: 32px;
    margin-right: 16px;
  }

  .item-category__title {
    margin-left: 16px;
    line-height: 32px;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
    flex: 1;
    min-width: 1px;
    color: #14171c;
    font-size: 15px;
  }

</style>
