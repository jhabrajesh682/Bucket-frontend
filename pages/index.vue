<template>
  <div>
    <v-row>
      <v-col cols="4">
        <v-text-field
              v-model="sessionName"
              label="Session name"
            ></v-text-field>
      </v-col>
      <v-col cols="8">
        <div style="text-align: center" class="pt-5">
          <v-btn
            depressed
            color="primary"
            @click="startNewSession"
          >
            New Session
          </v-btn>
          <v-btn
            depressed
            color="primary"
            @click="getSuggestions"
          >
            getSuggestion
          </v-btn>
        </div>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="4">
        <v-card>
          <v-card-title>
            Add the volume of the buckets
          </v-card-title>
          <v-card-text>
            <v-row>
              <v-col cols="2" class="headline">A:</v-col>
              <v-col cols="6">
                <v-text-field
                  type="number"
                  min="0"
                  :disabled="disableInputs"
                  v-model="bucketA"
                  outlined
                />
              </v-col>
              <v-col cols="4">
                cubic inches
              </v-col>
            </v-row>
            <v-row>
              <v-col cols="2" class="headline">B:</v-col>
              <v-col cols="6">
                <v-text-field
                  type="number"
                  :disabled="disableInputs"
                  v-model="bucketB"
                  outlined
                />
              </v-col>
              <v-col cols="4">
                cubic inches
              </v-col>
            </v-row>
            <v-row>
              <v-col cols="2" class="headline">C:</v-col>
              <v-col cols="6">
                <v-text-field
                  type="number"
                  :disabled="disableInputs"
                  v-model="bucketC"
                  outlined
                />
              </v-col>
              <v-col cols="4">
                cubic inches
              </v-col>
            </v-row>
            <v-row>
              <v-col cols="2" class="headline">D:</v-col>
              <v-col cols="6">
                <v-text-field
                  type="number"
                  :disabled="disableInputs"
                  v-model="bucketD"
                  outlined
                />
              </v-col>
              <v-col cols="4">
                cubic inches
              </v-col>
            </v-row>
            <v-row>
              <v-col cols="2" class="headline">E:</v-col>
              <v-col cols="6">
                <v-text-field
                  type="number"
                  :disabled="disableInputs"
                  v-model="bucketE"
                  outlined
                />
              </v-col>
              <v-col cols="4">
                cubic inches
              </v-col>
            </v-row>
          </v-card-text>
        </v-card>
      </v-col>
      <v-col cols="4">
        <v-card>
          <v-card-title>
            Add the volume of the balls
          </v-card-title>
          <v-card-text>
            <v-row>
              <v-col cols="2">Pink: </v-col>
              <v-col cols="6">
                <v-text-field
                  type="number"
                  :disabled="disableInputs"
                  v-model="pinkVol"
                  outlined
                />
              </v-col>
              <v-col cols="4">
                cubic inches
              </v-col>
            </v-row>
            <v-row>
              <v-col cols="2">Red: </v-col>
              <v-col cols="6">
                <v-text-field
                  type="number"
                  :disabled="disableInputs"
                  v-model="redVol"
                  outlined
                />
              </v-col>
              <v-col cols="4">
                cubic inches
              </v-col>
            </v-row>
            <v-row>
              <v-col cols="2">Blue: </v-col>
              <v-col cols="6">
                <v-text-field
                  type="number"
                  :disabled="disableInputs"
                  v-model="blueVol"
                  outlined
                />
              </v-col>
              <v-col cols="4">
                cubic inches
              </v-col>
            </v-row>
            <v-row>
              <v-col cols="2">Orange: </v-col>
              <v-col cols="6">
                <v-text-field
                  type="number"
                  :disabled="disableInputs"
                  v-model="orangeVol"
                  outlined
                />
              </v-col>
              <v-col cols="4">
                cubic inches
              </v-col>
            </v-row>
            <v-row>
              <v-col cols="2">Green: </v-col>
              <v-col cols="6">
                <v-text-field
                  type="number"
                  :disabled="disableInputs"
                  v-model="greenVol"
                  outlined
                />
              </v-col>
              <v-col cols="4">
                cubic inches
              </v-col>
            </v-row>
          </v-card-text>
        </v-card>
      </v-col>
      <v-col cols="4">
        <v-card>
          <v-card-title>
            Input the number of each colored
            ball to be placed inside the buckets:
          </v-card-title>
          <v-card-text>
            <v-row>
              <v-col cols="3">Pink:</v-col>
              <v-col cols="5">
                <v-text-field
                  type="number"
                  v-model="pinkQuant"
                  outlined
                />
              </v-col>
              <v-col cols="4">
                Balls
              </v-col>
            </v-row>
            <v-row>
              <v-col cols="3">Red:</v-col>
              <v-col cols="5">
                <v-text-field
                  type="number"
                  v-model="redQuant"
                  outlined
                />
              </v-col>
              <v-col cols="4">
                Balls
              </v-col>
            </v-row>
            <v-row>
              <v-col cols="3">Blue:</v-col>
              <v-col cols="5">
                <v-text-field
                  type="number"
                  v-model="blueQuant"
                  outlined
                />
              </v-col>
              <v-col cols="4">
                Balls
              </v-col>
            </v-row>
            <v-row>
              <v-col cols="3">Orange:</v-col>
              <v-col cols="5">
                <v-text-field
                  type="number"
                  v-model="orangeQuant"
                  outlined
                />
              </v-col>
              <v-col cols="4">
                Balls
              </v-col>
            </v-row>
            <v-row>
              <v-col cols="3">Green:</v-col>
              <v-col cols="5">
                <v-text-field
                  type="number"
                  v-model="greenQuant"
                  outlined
                />
              </v-col>
              <v-col cols="4">
                Balls
              </v-col>
            </v-row>
          </v-card-text>
        </v-card>
      </v-col>
      <v-dialog
        v-model="dialog"
        persistent
        width="500"
      >
        <v-card>
          <v-card-title>
            Suggestions
          </v-card-title>
  
          <v-card-text>
            {{ suggestionMsg }}
            <hr>
            <div class="pt-7">{{ emptyVolumeMsg }}</div>
          </v-card-text>
  
          <v-divider></v-divider>
  
          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn
              color="primary"
              text
              @click="dialog = false"
            >
              I accept
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
      <v-dialog
      v-model="errorDialog"
      max-width="290"
    >
      <v-card>
        <v-card-title class="text-h5">
          Error
        </v-card-title>

        <v-card-text>
          {{ errorMsg }}
        </v-card-text>

        <v-card-actions>
          <v-spacer></v-spacer>

          <v-btn
            color="green darken-1"
            text
            @click="errorDialog = false"
          >
            Cancel
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
    </v-row>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data () {
    return {
      buckets: [
        { name: 'A'}, { name: 'B'}, { name: 'C'}, { name: 'D'}, { name: 'E'}
      ],
      balls: ['Pink', 'Red', 'Blue', 'Orange', 'Green'],
      bucketA: null,
      bucketB: null,
      bucketC: null,
      bucketD: null,
      bucketE: null,
      pinkVol: 0,
      redVol: 0,
      blueVol: 0,
      orangeVol: 0,
      greenVol: 0,

      pinkQuant: 2,
      redQuant: 2,
      blueQuant: 2,
      orangeQuant: 2,
      greenQuant: 2,
      dialog: false,
      sessionName: null,
      newSession: false,
      disableInputs: false,
      errorDialog: false,
      errorMsg: null,
      suggestionMsg: '',
      emptyVolumeMsg: ''
    }
  },
  methods: {
   async getSuggestions() {
    const buckets = [
      { name: "a", volume: this.bucketA },
      { name: "b", volume: this.bucketB },
      { name: "c", volume: this.bucketC },
      { name: "d", volume: this.bucketD },
      { name: "e", volume: this.bucketE }
    ]
    const ballsVol = [
      { name: 'pink', volume: this.pinkVol},
      { name: 'red', volume: this.redVol},
      { name: 'blue', volume: this.blueVol},
      { name: 'green', volume: this.greenVol},
      { name: 'orange', volume: this.orangeVol},
    ]
    const numOfBalls = [
    { name: 'pink', quantity: parseFloat(this.pinkQuant)},
      { name: 'red', quantity: parseFloat(this.redQuant)},
      { name: 'blue', quantity: parseFloat(this.blueQuant)},
      { name: 'green', quantity: parseFloat(this.greenQuant)},
      { name: 'orange', quantity: parseFloat(this.orangeQuant)},
    ]
    const finalObj = {
      newSession: this.disableInputs ? false : true,
      sessionName: this.sessionName,
      bucketVolume: buckets,
      ballsVolume: ballsVol,
      numOfBalls: numOfBalls
    }
    if (this.sessionName === null) {
      this.errorDialog = true
      this.errorMsg = 'Please enter session name'
      return false
    }
    try {
      const {data} = await this.$axios.post(`http://localhost:8080/api/v1/bucket/getBallSuggestions`, finalObj)
      this.disableInputs = true
      let finalMsg = ''
      this.suggestionMsg = ''
      for (const iterator of data.result) {
        finalMsg += iterator.msg
        this.emptyVolumeMsg += `Empty volume of Bucket ${iterator.bucket} is ${iterator.emptyVolume}. `
      }
      this.suggestionMsg = finalMsg
      this.dialog = true

    } catch (error) {
      this.errorMsg = error
      this.errorDialog = true
    }
    },
   
    startNewSession() {
      this.sessionName = null
      this.newSession = true
      this.disableInputs = false
      this.bucketA = null
      this.bucketB = null
      this.bucketC = null
      this.bucketD = null
      this.bucketE = null
      this.pinkVol = 0
      this.redVol = 0
      this.BlueVol = 0
      this.orangeVol = 0
      this.greenVol = 0

      this.pinkQuant = 0
      this.redQuant = 0
      this.blueQuant = 0
      this.orangeQuant = 0
      this.greenQuant = 0
    }
  }
}
</script>
