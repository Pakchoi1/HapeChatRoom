<template>
  <div class="room-list">
    <h4>房间</h4>
    <hr />
    <b-list-group v-if="activeRoom">
      <b-list-group-item
        v-for="room in rooms"
        :key="room.name"
        :active="activeRoom.id === room.id"
        href="#"
        @click="onChange(room)"
      >
        # {{ room.name }}
      </b-list-group-item>
    </b-list-group>
  </div>
</template>

<script>
import {mapState, mapActions} from 'vuex'
export default {
  name: 'roomList',
  methods: {
    ...mapActions(
      [
        'changeRoom'
      ]
    ),
    onChange(room) {
      this.changeRoom(room.id);
    }
  },
  computed: {
    ...mapState(
      [
        'rooms',
        'activeRoom'
      ]
    )
  }
};
</script>

<style>
</style>