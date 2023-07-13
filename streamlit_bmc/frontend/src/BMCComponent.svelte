<script lang="ts">
  import { Streamlit, setStreamlitLifecycle } from './streamlit';
  import { onMount } from 'svelte';

  setStreamlitLifecycle();

  interface Card {
    id: number;
    text: string;
    enabled: boolean;
  }

  interface BmcType {
    visual: any;
    key_partners: { cards: Card[] };
    key_activities: { cards: Card[] };
    key_resources: { cards: Card[] };
    value_propositions: { cards: Card[] };
    customer_relationship: { cards: Card[] };
    channels: { cards: Card[] };
    customer_segments: { cards: Card[] };
    cost_structure: { cards: Card[] };
    revenue_streams: { cards: Card[] };
  }

  export let data: BmcType;

  let cardState: Card[] = [];

  onMount(() => {
    cardState = data.key_partners.cards.map((card) => ({ ...card, enabled: true }));
    console.log(cardState);
  });

  function toggleCardState(idx: number) {
    cardState[idx].enabled = !cardState[idx].enabled;
  }
</script>

<!-- Main -->
<div class="container-fluid text-center">
  <h1 class="bmc-title">{data.visual.company_name} - Business Model Canvas</h1>
</div>
<div class="container-fluid grids">
  <div class="grid grid-top">
    <div class="model-item partner">
      <div class="item-heading">
        <i class="icon icon-1 icon-par" />
        <span>Key Partners</span>
      </div>
      <div class="cards">
        {#each data.key_partners.cards as { id, text }, idx}
          <div
            id="partner-{id}"
            class="note note-1 {cardState[idx]?.enabled ? 'enabled' : 'disabled'}"
            on:click={() => toggleCardState(idx)}
            on:keydown={() => {}}
          >
            {text}
          </div>
        {/each}
      </div>
    </div>
    <div class="model-item activities">
      <div class="item-heading">
        <i class="icon icon-2 icon-act" />
        <span>Key Activities</span>
      </div>
      <div class="cards">
        {#each data.key_activities.cards as { id, text }, idx}
          <div id="activity-{id}" class="note note-2">{text}</div>
        {/each}
      </div>
    </div>
    <div class="model-item resources">
      <div class="item-heading">
        <i class="icon icon-3 icon-res" />
        <span>Key Resources</span>
      </div>
      <div class="cards">
        {#each data.key_resources.cards as { id, text }, idx}
          <div id="activity-{id}" class="note note-3">
            <span>{text}</span>
          </div>
        {/each}
      </div>
    </div>
    <div class="model-item value-p">
      <div class="item-heading">
        <i class="icon icon-4 icon-val" />
        <span>Value Propositions</span>
      </div>
      <div class="cards">
        {#each data.value_propositions.cards as { id, text }, idx}
          <div id="resource-{id}" class="note note-4">{text}</div>
        {/each}
      </div>
    </div>
    <div class="model-item customer-r">
      <div class="item-heading">
        <i class="icon icon-5 icon-rel" />
        <span>Customer Relationship</span>
      </div>
      <div class="cards">
        {#each data.customer_relationship.cards as { id, text }, idx}
          <div id="value-{id}" class="note note-5">{text}</div>
        {/each}
      </div>
    </div>
    <div class="model-item channels">
      <div class="item-heading">
        <i class="icon icon-6 icon-cha" />
        <span>Channels</span>
      </div>
      <div class="cards">
        {#each data.channels.cards as { id, text }, idx}
          <div id="channel-{id}" class="note note-6">{text}</div>
        {/each}
      </div>
    </div>
    <div class="model-item customer-s">
      <div class="item-heading">
        <i class="icon icon-7 icon-seg" />
        <span>Customer Segments</span>
      </div>
      <div class="cards">
        {#each data.customer_segments.cards as { id, text }, idx}
          <div id="segment-{id}" class="note note-7">{text}</div>
        {/each}
      </div>
    </div>
  </div>
  <div class="grid grid-bottom grid-vertical">
    <div class="model-item cost">
      <div class="item-heading">
        <i class="icon icon-8 icon-cos" />
        <span>Cost Structure</span>
      </div>
      <div class="cards">
        {#each data.cost_structure.cards as { id, text }, idx}
          <div id="cost-{id}" class="note note-8">{text}</div>
        {/each}
      </div>
    </div>
    <div class="model-item revenue">
      <div class="item-heading">
        <i class="icon icon-9 icon-rev" />
        <span>Revenue Streams</span>
      </div>
      <div class="cards">
        {#each data.revenue_streams.cards as { id, text }, idx}
          <div id="cost-{id}" class="note note-9">{text}</div>
        {/each}
      </div>
    </div>
  </div>
</div>
<div class="pr text-right">&copy; Business Model Canvas</div>
