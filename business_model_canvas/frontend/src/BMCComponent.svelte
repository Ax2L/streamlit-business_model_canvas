<script lang="ts">
  import { Streamlit, setStreamlitLifecycle } from "./streamlit";
  setStreamlitLifecycle();

  interface BmcType {
    visual: any;
    key_partners: any;
    key_activities: any;
    key_resources: any;
    value_propositions: any;
    customer_relationship: any;
    channels: any;
    customer_segments: any;
    cost_structure: any;
    revenue_streams: any;
  }

  export let data: BmcType;
  export let disabled: boolean;
</script>

<!-- Main -->
<div class="container text-center">
  <h1>{data.visual.company_name} - Business Model Canvas</h1>
</div>
<div class="container-fluid grids">
  <div class="grid grid-top">
    <div class="model-item partner">
      <div class="item-heading">
        <span>Key Partners</span>
        <i class="bi bi-link-45deg"></i>
      </div>
      <div class="cards">
        {#each data.key_partners.cards as { id, text }, idx}
        <div id="partner-{id}" class="card"> {text} </div>
        {/each}
      </div>
    </div>
    <div class="model-item activities">
      <div class="item-heading">
        <span>Key Activities</span>
        <i class="bi bi-activity"></i>
      </div>
      <div class="cards">
        {#each data.key_activities.cards as { id, text }, idx}
        <div id="activity-{id}" class="card">{text} </div>
        {/each}
      </div>
    </div>
    <div class="model-item resources">
      <div class="item-heading">
        <span>Key Resources</span>
        <i class="bi bi-buildings"></i>
      </div>
      <div class="cards">
        {#each data.key_resources.cards as { id, text }, idx}
        <div id="activity-{id}" class="card">{text} </div>
        {/each}
      </div>
    </div>
    <div class="model-item value-p">
      <div class="item-heading">
        <span>Value Propositions</span>
        <i class="bi bi-gift"></i>
      </div>
      <div class="cards">
        {#each data.value_propositions.cards as { id, text }, idx}
        <div id="resource-{id}" class="card">{text} </div>
        {/each}
      </div>
    </div>
    <div class="model-item customer-r">
      <div class="item-heading">
        <span>Customer Relationship</span>
        <i class="bi bi-heart"></i>
      </div>
      <div class="cards">
        {#each data.customer_relationship.cards as { id, text }, idx}
        <div id="value-{id}" class="card">{text} </div>
        {/each}
      </div>
    </div>
    <div class="model-item channels">
      <div class="item-heading">
        <span>Channels</span>
        <i class="bi bi-truck"></i>
      </div>
      <div class="cards">
        {#each data.channels.cards as { id, text }, idx}
        <div id="channel-{id}" class="card">{text} </div>
        {/each}
      </div>
    </div>
    <div class="model-item customer-s">
      <div class="item-heading">
        <span>Customer Segments</span>
        <i class="bi bi-person-gear"></i>
      </div>
      <div class="cards">
        {#each data.customer_segments.cards as { id, text }, idx}
        <div id="segment-{id}" class="card">{text} </div>
        {/each}
      </div>
    </div>
  </div>
  <div class="grid grid-bottom grid-vertical">
    <div class="model-item cost">
      <div class="item-heading">
        <span>Cost Structure</span>
        <i class="bi bi-coin"></i>
      </div>
      <div class="cards">
        {#each data.cost_structure.cards as { id, text }, idx}
        <div id="cost-{id}" class="card">{text} </div>
        {/each}
      </div>
    </div>
    <div class="model-item revenue">
      <div class="item-heading">
        <span>Revenue Streams</span>
        <i class="bi bi-graph-up-arrow"></i>
      </div>
      <div class="cards">
        {#each data.revenue_streams.cards as { id, text }, idx}
        <div id="cost-{id}" class="card">{text} </div>
        {/each}
      </div>
    </div>
  </div>
</div>
<div class="pr text-right">&copy; Business Model Canvas</div>
