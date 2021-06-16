<template>
  <tbody class="t-body">
    <tr v-for="(user, index) in users" :key="user.id">
      <td>
        <input
          type="checkbox"
          :value="user.id"
          v-model="activeUsers"
          :class="{ disabled: user.id === lastUser }"
        />
      </td>
      <td>{{ user.id }}</td>
      <td>
        <router-link :to="{ name: 'users', params: { userId: user.id } }"
          >Подробнее</router-link
        >
      </td>
      <td>{{ user.username }}</td>
      <td>{{ user.email }}</td>
      <td>{{ user.website }}</td>
      <td @click="deleteRow(index)" class="deleteTable">x</td>
    </tr>
  </tbody>
</template>

<script>

export default {
  data: () => ({
    activeUsers: [1],
    users: null,
    disabled: false,
  }),
  computed: {
    lastUser() {
      let num = null;
      if (this.activeUsers.length < 2) {
        this.activeUsers.forEach((element) => {
          num = element;
        });
      }
      return num;
    },
  },
  methods: {
    deleteRow(index) {
      this.users.splice(index, 1);
    },
  },
  created() {
    this.$axios
      .get("https://jsonplaceholder.typicode.com/users")
      .then((response) => (this.users = response.data));
  },
};
</script>

<style lang="scss">
.disabled {
  pointer-events: none;
}
.t-body {
  td {
    padding: 10px 25px;
  }
  .deleteTable {
    cursor: pointer;
    font-size: 25px;
  }
}
</style>