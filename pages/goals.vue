<template>
  <div>
    <v-card color="primary" class="my-4" outlined>
      <v-card-title>Home Workouts</v-card-title>
      <v-card-text>
        Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
      </v-card-text>
    </v-card>

    <v-card color="secondary" class="my-4" outlined>
      <v-card-title>Completed this week</v-card-title>
      <h1 class="text-center">{{ completed }}/{{ total }}</h1>
    </v-card>

    <v-card color="accent" class="my-4" outlined>
      <v-card-title>Tick it off</v-card-title>
      <div class="ml-6">
        <v-checkbox v-model="day1" label="Workout 1" />
        <v-checkbox v-model="day2" label="Workout 2" />
        <v-checkbox v-model="day3" label="Workout 3" />
      </div>
    </v-card>
  </div>
</template>

<script>
export default {
  data: () => ({
    baseCompleted: 100,
    total: 678,
    day1: false,
    day2: false,
    day3: false
  }),

  computed: {
    completed () {
      const tickedOff = this.day1 && this.day2 && this.day3
      const extra = tickedOff ? 1 : 0
      return this.baseCompleted + extra
    }
  }
}
</script>
