<template>
  <q-page class="q-pa-md">
    <div class="q-pa-md">
      <div class="q-gutter-y-md">
        <h3>
          BENCHMARKING YOUR DIGITAL TRANSFORMATION JOURNEY
        </h3>
        <p>
          To plan your digital transformation journey, you need to understand where you are today—a process that involves assessing your own digital maturity (including cataloging the digital initiatives you already have underway), as well as benchmarking yourself against your middle market peers.
        </p>
        <h6>
          Assessing Your Own Digital Maturity
        </h6>
        <p>
          Assessing your current digital state is critical to setting attainable goals, maximizing existing assets, and developing an executable roadmap grounded in reality. While competitive benchmarking should be performed in the context of industry, in general, businesses should follow a digital maturity assessment framework.
        </p>
        <p>
          This approach features three key areas of transformation: business model maturity (Digital Business), operations maturity (Digital Process), and IT maturity (Digital Backbone).
        </p>
        <p>
          These three transformation areas overlap and are inextricably connected—and will become even more interlocked as your organization becomes increasingly digital. Having a solid baseline understanding of how you rank in each area can help you identify and bridge critical gaps, and move you closer to achieving your vision.
        </p>
        <h6>
          Benchmarking Against Your Peers
        </h6>
        <p>
          The second benchmarking consideration is simple: How do you stack up against your middle market peers? While each industry is different, benchmarking can help you determine the priority areas of focus for your digital transformation efforts.
        </p>
        <h4>
          1. What’s Your Status? Current Digital Transformation Plans
        </h4>
        <bar-chart />
        <h4>
          2. How Strong is Your Digital Backbone? Current IT Infrastructure’s Ability to Integrate Advanced Technologies
        </h4>
        <digi-back-chart/>
        <h4>
          Insight
        </h4>
        <p>
          While many executives may think highly of their current IT infrastructure’s ability to integrate advanced technologies—along with how their digital capabilities compare to those of their industry peers—the fact is, 
          that’s not always reflective of reality. 
          It actually depends on the companies' organizational size, and industry.
        </p>
        <p>
          Views between tech (e.g. CIO, CISO, CTO) and non-tech (e.g. CEO, CFO, COO, CMO) C-suite executives, 
          for example, often differed significantly: 78 percent of non-tech C-suite executives view their organization’s IT integration capabilities as “very good” or “excellent,” 
          compared to only 48 percent of tech C-suite executives.
        </p>
        <p>
          Similarly, 45 percent of non-tech C-suite executives rate their company’s digital capabilities as “advanced” compared to their peers, versus only 26 percent of those in the tech C-suite. 
          These differences imply that executives, even in the same organization, don’t necessarily share the same awareness or understanding of their organization’s digital capabilities—with non-tech C-suite executives’ views tending to be more favorable than those in tech roles.
        </p>
      </div>
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'
import BarChart from '../components/BarChart'
import DigiBackChart from '../components/DigitalBackboneChart.vue'
export default defineComponent({
  name: 'Benchmark',
  components: {
    BarChart,
    DigiBackChart
  },
  setup () {
  },
  data () {
    return {
    }
  },
})
</script>
<style lang="sass" scoped>
</style>