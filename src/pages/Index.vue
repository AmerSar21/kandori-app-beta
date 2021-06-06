<template>
  <q-page class="flex-center q-pa-md">
    <div class="items-center text-center" :class="$q.screen.lt.xl ? '' : 'row'">
      <q-card class="bg-white-5 q-pa-xl col-6">
        <q-card-section>
          <q-input
            v-model="search"
            debounce="500"
            filled
            placeholder="Search Kandori.."
          >
            <template v-slot:append>
              <q-icon name="search" />
            </template>
          </q-input>
        </q-card-section>
      </q-card>
      <br />
      <q-card class="bg-white-5 q-pa-xl col-6">
        <q-card-section> </q-card-section>
        <q-card-actions vertical align="center">
          <q-card-actions
            ><q-btn label="Restaurant" to="/resto"></q-btn>
          </q-card-actions>
        </q-card-actions>
      </q-card>
    </div>
  </q-page>
</template>

<script lang="ts">
import { Todo, Meta } from 'components/models';
import ExampleComponent from 'components/ClassComponent.vue';
import { Vue, Component } from 'vue-property-decorator';

@Component({
  components: { ExampleComponent }
})
export default class PageIndex extends Vue {
  search: string = "";
  todos: Todo[] = [
    {
      id: 1,
      content: 'ct1'
    },
    {
      id: 2,
      content: 'ct2'
    },
    {
      id: 3,
      content: 'ct3'
    },
    {
      id: 4,
      content: 'ct4'
    },
    {
      id: 5,
      content: 'ct5'
    }
  ];
  meta: Meta = {
    totalCount: 1200
  };
}
</script>
