<template>
  <div class="event">
    <div class="name">
      {{ event.name[locale] }}
    </div>
    <div class="meta">
      {{ displayHour(content.startAt) }} - {{ displayHour(content.endAt) }}
    </div>
  </div>
</template>

<script setup lang="ts">
import { type TimeTableEvent, type TimeTableContents } from '~/models/model'
const { locale } = useI18n()
const { session, timetable } = defineProps({
  content: {} as PropType<TimeTableContents>,
  event: {} as PropType<TimeTableEvent>
})
</script>

<style scoped lang="scss">
.event {
  text-align: center;
  text-align: left;
  padding: 24px 30px;

  @media screen and (max-width: $headerViewport - 1) {
    padding: 24px 16px;
  }
}
.name {
  font-weight: bold;
  font-size: 20px;

  @media screen and (max-width: $headerViewport - 1) {
    font-size: 16px;
  }
}

.meta {
  color: #888;
}

</style>
