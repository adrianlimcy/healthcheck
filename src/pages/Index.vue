<template>
  <q-page class="q-pa-md">
    <div class="q-pa-md">
      <div class="q-gutter-y-md">
        <q-card>
          <q-tabs
            v-model="tab"
            dense
            class="text-grey"
            active-color="primary"
            indicator-color="primary"
            align="justify"
            narrow-indicator
          >
            <q-tab name="digitalization" label="Digitalization Journey" />
            <q-tab name="office_safety" label="Office Safety" />
            <q-tab name="office_clean" label="Office Cleanliness" />
          </q-tabs>

          <q-separator />

          <q-tab-panels v-model="tab" animated>
            <q-tab-panel name="digitalization">
              <div class="text-h6">Digitization | Past</div>
              <q-list>
                <q-item tag="label" v-ripple>
                  <q-item-section avatar>
                    <q-checkbox v-model="paperRec" val=true color="teal" @click='onPaperRec'/>
                  </q-item-section>
                   <q-item-section>
                    <q-item-label>Paper Records to Digital Records</q-item-label>
                    <q-item-label caption>
                      Are your hard copy documents scanned & converted into digital format?
                      <p>Typically past 5 years for compliance.</p>
                    </q-item-label>
                  </q-item-section>
                </q-item>

                <q-item tag="label" v-ripple>
                  <q-item-section avatar>
                    <q-checkbox v-model="dataExt" val=true color="orange" @click='onDataExt'/>
                  </q-item-section>
                  <q-item-section>
                    <q-item-label>Database | Data Extraction</q-item-label>
                    <q-item-label caption>
                      Is there a storage system (database) for all the digital formatted documents?
                    </q-item-label>
                  </q-item-section>
                </q-item>

                <q-item tag="label" v-ripple>
                  <q-item-section avatar top>
                    <q-checkbox v-model="metadata" val=true color="cyan" @click='onMetadata'/>
                  </q-item-section>
                  <q-item-section>
                    <q-item-label>Metadata Creation</q-item-label>
                    <q-item-label caption>
                      Are the digital documents indexed for searching purposes?
                    </q-item-label>
                  </q-item-section>
                </q-item>
               
                <q-item tag="label" v-ripple>
                  <q-item-section avatar top>
                    <q-checkbox v-model="contentMgt" val=true color="purple" @click='onContentMgt'/>
                  </q-item-section>
                  <q-item-section>
                    <q-item-label>Digital Content Management</q-item-label>
                    <q-item-label caption>
                      Do you have a platform to search and download the documents (e.g. pdf) for reference?
                    </q-item-label>
                  </q-item-section>
                </q-item>
              </q-list>
              
              <div class="text-h6">Digitalization | Present</div>
              <q-list>
                <q-item tag="label" v-ripple>
                  <q-item-section avatar>
                    <q-checkbox v-model="eForm" val="true" color="teal" @click='onEForm'/>
                  </q-item-section>
                  <q-item-section>
                    <q-item-label>Electronic Forms</q-item-label>
                    <q-item-label caption>
                      Do you use electronic forms instead of manual paper forms currently?
                      <p>(e.g. Order Processing, HR onboarding / exit)</p>
                    </q-item-label>
                  </q-item-section>
                </q-item>

                <q-item tag="label" v-ripple>
                  <q-item-section avatar>
                    <q-checkbox v-model="digiWk" val="true" color="orange" @click='onDigiWk'/>
                  </q-item-section>
                  <q-item-section>
                    <q-item-label>Digital Workflow</q-item-label>
                    <q-item-label caption>
                      Do you have an approval escalation for your electronic forms?
                      <p>(e.g. Claims to manager approval to Payment)</p>
                    </q-item-label>
                  </q-item-section>
                </q-item>

                <q-item tag="label" v-ripple>
                  <q-item-section avatar top>
                    <q-checkbox v-model="proAuto" val="true" color="cyan" @click='onProAuto'/>
                  </q-item-section>
                  <q-item-section>
                    <q-item-label>Process Automation</q-item-label>
                    <q-item-label caption>
                      Can your customers access their invoices and billing history remotely?
                    </q-item-label>
                  </q-item-section>
                </q-item>

                <q-item tag="label" v-ripple>
                  <q-item-section avatar top>
                    <q-checkbox v-model="macLearning" val="true" color="purple" @click='onMacLearning'/>
                  </q-item-section>
                  <q-item-section>
                    <q-item-label>Machine Learning /  IoT</q-item-label>
                    <q-item-label caption>
                      Do you have a chatbot or any RPA bots in your company?
                    </q-item-label>
                  </q-item-section>
                </q-item>
              </q-list>
              
              <div class="text-h6">Digital Transformation | Future</div>
              <q-list>

                <q-item tag="label" v-ripple>
                  <q-item-section avatar>
                    <q-checkbox v-model="dataAna" val="true" color="teal" @click='onDataAna'/>
                  </q-item-section>
                  <q-item-section>
                    <q-item-label>Data Analytics</q-item-label>
                    <q-item-label caption>
                      Does anyone in the company analyse your data?
                      <p>e.g. Web traffic, customer base, trends ... etc</p>
                    </q-item-label>
                  </q-item-section>
                </q-item>

                <q-item tag="label" v-ripple>
                  <q-item-section avatar>
                    <q-checkbox v-model="dataWh" val="true" color="orange" @click='onDataWh'/>
                  </q-item-section>
                  <q-item-section>
                    <q-item-label>Data Warehousing</q-item-label>
                    <q-item-label caption>
                      Do you store your data in a safe and secure environment?
                      <p>e.g BCP, Redundancy, ... etc</p>
                    </q-item-label>
                  </q-item-section>
                </q-item>

                <q-item tag="label" v-ripple>
                  <q-item-section avatar top>
                    <q-checkbox v-model="bizInt" val="true" color="cyan" @click='onBizInt'/>
                  </q-item-section>
                  <q-item-section>
                    <q-item-label>Business Intelligence / AI</q-item-label>
                    <q-item-label caption>
                      Does your system recommend & formulate business strategies from analytics?
                    </q-item-label>
                  </q-item-section>
                </q-item>

                <q-item tag="label" v-ripple>
                  <q-item-section avatar top>
                    <q-checkbox v-model="chgMgt" val="true" color="purple" @click='onChgMgt'/>
                  </q-item-section>
                  <q-item-section>
                    <q-item-label>Change Management</q-item-label>
                    <q-item-label caption>
                      Do you have a Change Management Program when running enhancement to your internal office operations?
                    </q-item-label>
                  </q-item-section>
                </q-item>
              </q-list>

               <div class="q-pa-md q-gutter-sm">
                Score {{totalDigi}} / 100
               </div>
            </q-tab-panel>

            <q-tab-panel name="office_safety">              
              <div class="text-h6">Capacity Management</div>
              <q-list>
                <q-item tag="label" v-ripple>
                  <q-item-section avatar>
                    <q-checkbox v-model="arrangement" val="true" color="teal" @click='onArrangement'/>
                  </q-item-section>
                  <q-item-section>
                    <q-item-label>Team Arrangements</q-item-label>
                    <q-item-label caption>
                      Is there a tool for arrangement of split teams for office physical presence?
                    </q-item-label>
                  </q-item-section>
                </q-item>

                <q-item tag="label" v-ripple>
                  <q-item-section avatar>
                    <q-checkbox v-model="socialDist" val="true" color="orange" @click='onSocialDist'/>
                  </q-item-section>
                  <q-item-section>
                    <q-item-label>Social Distancing</q-item-label>
                    <q-item-label caption>
                      Is there a tool for workstation social distancing compliance?
                    </q-item-label>
                  </q-item-section>
                </q-item>

                <q-item tag="label" v-ripple>
                  <q-item-section avatar top>
                    <q-checkbox v-model="capMgt" val="true" color="cyan" @click='onCapMgt'/>
                  </q-item-section>
                  <q-item-section>
                    <q-item-label>Capacity Management</q-item-label>
                    <q-item-label caption>
                      Is there a tool for capacity management?
                    </q-item-label>
                  </q-item-section>
                </q-item>

                <q-item tag="label" v-ripple>
                  <q-item-section avatar top>
                    <q-checkbox v-model="rec" val="true" color="purple" @click='onRec'/>
                  </q-item-section>
                  <q-item-section>
                    <q-item-label>Records</q-item-label>
                    <q-item-label caption>
                      Are the records kept digitally for accountability and accessability?
                    </q-item-label>
                  </q-item-section>
                </q-item>
              </q-list>

               <div class="q-pa-md q-gutter-sm">
                Score {{totalSafety}} / 100
               </div>
            </q-tab-panel>

            <q-tab-panel name="office_clean">
              <div class="text-h6">Office Cleanliness</div>
              <q-list>
                <q-item tag="label" v-ripple>
                  <q-item-section avatar>
                    <q-checkbox v-model="cleanOffice" val=true color="teal" @click='onCleanOff'/>
                  </q-item-section>
                   <q-item-section>
                    <q-item-label>Cleaning Device</q-item-label>
                    <q-item-label caption>
                      Do you have a cleaning / disinfecting / sanitizing device for the office?
                    </q-item-label>
                  </q-item-section>
                </q-item>

                <q-item tag="label" v-ripple>
                  <q-item-section avatar>
                    <q-checkbox v-model="schClean" val=true color="orange" @click='onSchClean'/>
                  </q-item-section>
                  <q-item-section>
                    <q-item-label>Scheduled Cleaning</q-item-label>
                    <q-item-label caption>
                      Do you do weekly area cleaning?
                    </q-item-label>
                  </q-item-section>
                </q-item>

                <q-item tag="label" v-ripple>
                  <q-item-section avatar top>
                    <q-checkbox v-model="cleanList" val=true color="cyan" @click='onCleanList'/>
                  </q-item-section>
                  <q-item-section>
                    <q-item-label>Cleaning Checklist</q-item-label>
                    <q-item-label caption>
                      Do you have a cleaner's checklist?
                      <p>e.g. Frequency of where to do cleaning? Touch points?</p>
                    </q-item-label>
                  </q-item-section>
                </q-item>
               
                <q-item tag="label" v-ripple>
                  <q-item-section avatar top>
                    <q-checkbox v-model="filSys" val=true color="purple" @click='onFilSys'/>
                  </q-item-section>
                  <q-item-section>
                    <q-item-label>Filtration System</q-item-label>
                    <q-item-label caption>
                      Is there a filtration system in the office?
                    </q-item-label>
                  </q-item-section>
                </q-item>

                <q-item tag="label" v-ripple>
                  <q-item-section avatar top>
                    <q-checkbox v-model="ahu" val=true color="pink" @click='onAhu'/>
                  </q-item-section>
                  <q-item-section>
                    <q-item-label>AHU</q-item-label>
                    <q-item-label caption>
                      Is the AHU air cleansed and purified frequently?
                    </q-item-label>
                  </q-item-section>
                </q-item>
              </q-list>
               <div class="q-pa-md q-gutter-sm">
                Score {{totalClean}} / 100
               </div>
            </q-tab-panel>
          </q-tab-panels>
        </q-card>
      </div>
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'
import { ref } from 'vue'

export default defineComponent({
  name: 'PageIndex',
  setup () {
    return {
      tab: ref('digitalization'),
      paperRec: ref([]),
      dataExt: ref([]),
      metadata: ref([]),
      contentMgt: ref([]),
      eForm: ref([]),
      digiWk: ref([]),
      proAuto: ref([]),
      macLearning: ref([]),
      dataAna: ref([]),
      dataWh: ref([]),
      bizInt: ref([]),
      chgMgt: ref([]),
      cleanOffice: ref([]),
      schClean: ref ([]),
      cleanList: ref([]),
      filSys: ref([]),
      ahu: ref([]),
      arrangement: ref([]),
      socialDist: ref([]),
      capMgt: ref([]),
      rec: ref([])
    }
  },
  data () {
    return {
      totalDigi: 0,
      totalClean: 0,
      totalSafety: 0
    }
  },
  computed: {    
  },
  methods: {
    onPaperRec () {
      this.paperRec[0]=='true' ? this.totalDigi = this.totalDigi + 10 : this.totalDigi = this.totalDigi - 10
    },
    onDataExt () {
      this.dataExt[0]=='true' ? this.totalDigi = this.totalDigi + 5 : this.totalDigi = this.totalDigi - 5
    },
    onMetadata () {
      this.metadata[0]=='true' ? this.totalDigi = this.totalDigi + 5 : this.totalDigi = this.totalDigi - 5
    },
    onContentMgt () {
      this.contentMgt[0]=='true' ? this.totalDigi = this.totalDigi + 20 : this.totalDigi = this.totalDigi - 20
    },
    onEForm () {
      this.eForm[0]=='true' ? this.totalDigi = this.totalDigi + 15 : this.totalDigi = this.totalDigi - 15
    },
    onDigiWk () {
      this.digiWk[0]=='true' ? this.totalDigi = this.totalDigi + 10 : this.totalDigi = this.totalDigi - 10
    },
    onProAuto () {
      this.proAuto[0]=='true' ? this.totalDigi = this.totalDigi + 10 : this.totalDigi = this.totalDigi - 10
    },
    onMacLearning () {
      this.macLearning[0]=='true' ? this.totalDigi = this.totalDigi + 5 : this.totalDigi = this.totalDigi - 5
    },
    onDataAna () {
      this.dataAna[0]=='true' ? this.totalDigi = this.totalDigi + 5 : this.totalDigi = this.totalDigi - 5
    },
    onDataWh () {
      this.dataWh[0]=='true' ? this.totalDigi = this.totalDigi + 5 : this.totalDigi = this.totalDigi - 5
    },
    onBizInt () {
      this.bizInt[0]=='true' ? this.totalDigi = this.totalDigi + 5 : this.totalDigi = this.totalDigi - 5
    },
    onChgMgt () {
      this.chgMgt[0]=='true' ? this.totalDigi = this.totalDigi + 5 : this.totalDigi = this.totalDigi - 5
    },
    onCleanOff () {
      this.cleanOffice[0]=='true' ? this.totalClean = this.totalClean + 5 : this.totalClean = this.totalClean - 5
    },
    onSchClean () {
      this.schClean[0]=='true' ? this.totalClean = this.totalClean + 5 : this.totalClean = this.totalClean - 5
    },
    onCleanList () {
      this.cleanList[0]=='true' ? this.totalClean = this.totalClean + 5 : this.totalClean = this.totalClean - 5
    },
    onFilSys () {
      this.filSys[0]=='true' ? this.totalClean = this.totalClean + 5 : this.totalClean = this.totalClean - 5
    },
    onAhu () {
      this.ahu[0]=='true' ? this.totalClean= this.totalClean + 5 : this.totalClean = this.totalClean - 5
    },
    onArrangement () {
      this.arrangement[0]=='true' ? this.totalSafety = this.totalSafety + 5 : this.totalSafety = this.totalSafety - 5
    },
    onSocialDist () {
      this.socialDist[0]=='true' ? this.totalSafety = this.totalSafety + 5 : this.totalSafety = this.totalSafety - 5
    },
    onCapMgt () {
      this.capMgt[0]=='true' ? this.totalSafety = this.totalSafety + 5 : this.totalSafety = this.totalSafety - 5
    },
    onRec () {
      this.rec[0]=='true' ? this.totalSafety = this.totalSafety + 5 : this.totalSafety = this.totalSafety - 5
    }      
  }
})
</script>
