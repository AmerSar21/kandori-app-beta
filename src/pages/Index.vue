<template>
  <q-page class="flex-center q-pa-md">
    <div class="items-center text-center" :class="$q.screen.lt.xl ? '' : 'row'">
      <!-- <q-card class="bg-white-5 q-pa-xl col-6">
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
      </q-card> -->
      <div
        class="text-center"
        :class="$q.screen.lt.md ? 'q-pt-md' : 'q-py-md q-pt-xl'"
      >
        <div
          class="text-primary"
          :class="$q.screen.lt.md ? 'text-h3' : 'text-h1'"
        >
          KOMAN TANO!
        </div>
        <div
          class="text-grey-9"
          :class="$q.screen.lt.md ? 'text-subtitle1' : 'text-h5'"
        >
          Giving your hunger a new option
        </div>
      </div>
      <div
        class="flex flex-center"
        :class="$q.screen.lt.md ? 'q-pt-lg' : 'q-pt-xl q-pb-lg'"
      >
        <q-card
          class="my-card shadow-10 row"
          :style="$q.screen.lt.md ? 'width: 320px' : 'width: 50%'"
        >
          <q-card-section class="col q-pa-sm">
            <q-select
              v-model="search"
              outlined
              label="Search Restaurant"
              label-color="primary"
              color="primary"
              input-debounce="0"
              use-input
              clearable
              clear-icon
              hide-dropdown-icon
            >
              <template v-slot:append>
                <q-icon name="search" />
              </template>
              <template v-slot:no-option>
                <q-item>
                  <q-item-section class="text-grey">
                    No results
                  </q-item-section>
                </q-item>
              </template>
            </q-select>
          </q-card-section>
        </q-card>
      </div>

      <div
        :class="
          $q.screen.lt.md
            ? 'q-mt-xl flex flex-center'
            : 'row justify-between q-mt-md'
        "
        style="padding: 0px 65px 0px 65px"
      >
        <span class="text-h4 text-grey-9 text-weight-bold q-pb-sm"
          >Restaurants</span
        >
        <q-select
          dense
          outlined
          style="width: 200px"
          label="Category"
          label-color="primary"
          color="primary"
        />
      </div>
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
  search: string = '';
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
