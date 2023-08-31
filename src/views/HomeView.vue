<template>
  <div class="">
    <div v-if="!isSubmited" class="container">
      <h1>Customized SOP Generator</h1>
      <form action="javascript:;" @submit="Submit()">
        <div class="row">
          <!-- //email -->
          <div class="mb-3 col-sm-12 col-md-6 col-lg-4">
            <label for="exampleInputEmail1" class="form-label">Email </label>
            <input
              type="text"
              class="form-control"
              placeholder="Your email address"
              name="email"
              v-model="email"
              required
            />
          </div>
          <!-- //fullname -->
          <div class="mb-3 col-sm-12 col-md-6 col-lg-4">
            <label for="exampleInputName" class="form-label">Full Name</label>

            <input
              type="text"
              class="form-control"
              placeholder="your full name"
              name="name"
              required
              v-model="fullName"
            />
          </div>
          <!-- age -->
          <div class="mb-3 col-sm-12 col-md-6 col-lg-4">
            <label for="exampleInputAge" class="form-label">Age</label>
            <input
              type="Number"
              class="form-control"
              placeholder="Enter age"
              name="age"
              required
              v-model="age"
            />
          </div>
          <!-- Highest Level of Education -->
          <div class="mb-3 col-sm-12 col-md-6 col-lg-4">
            <label for="exampleInputEducation" class="form-label"
              >Highest Level of Education</label
            >

            <select
              class="form-select"
              aria-label="Default select example"
              required
              v-model="highestEducation"
            >
              <option data-hidden="true">Choose Option</option>
              <option value="Grade 12">Grade 12</option>
              <option value="Diploma">Diploma</option>
              <option value="Bachelors Degree">Bachelors Degree</option>
              <option value="Masters Degree">Masters Degree</option>
              <option value="phD">PhD</option>
            </select>
          </div>
          <!-- Institute where you completed your highest level of
              education -->
          <div class="mb-3 col-sm-12 col-md-6 col-lg-4">
            <label for="exampleInputHighestStudy" class="form-label"
              >Institute where you completed your highest level of
              education</label
            >
            <input
              type="text"
              class="form-control"
              placeholder="institute name"
              name="institute"
              required
              v-model="graduationCollege"
            />
          </div>
          <!-- What did you study -->
          <div class="mb-3 col-sm-12 col-md-6 col-lg-4">
            <label for="exampleInputStudyDesc" class="form-label"
              >What did you study
            </label>
            <input
              type="text"
              class="form-control"
              placeholder="Your answer"
              name="study"
              required
              v-model="stream"
            />
          </div>
          <!-- experience -->
          <div class="mb-3 col-sm-12 col-md-6 col-lg-4">
            <label for="exampleInputStudyDesc" class="form-label"
              >Do you have any relevant work experience? <br />
              Write None if no work experience. Provide the following details if
              yes: <br />
              <!-- <ol>
                <li>Job Title</li>
                <li>Company Name</li>
                <li>Job duties</li>
              </ol>
              <p>
                Sample Answer: I worked as a Sales Manager at Effizient
                Immigration Inc from Jan 2022 till Feb 2023. In this role, I
                managed sales operations, reaching out to leads, lead the
                outreach program, ensured meeting monthly targets.
              </p> -->
            </label>
            <input
              type="text"
              class="form-control"
              placeholder="Your answer"
              name="experience"
              required
              v-model="experience"
            />
          </div>
          <!-- What institute did you get admitted to in Canada -->
          <div class="mb-3 col-sm-12 col-md-6 col-lg-4">
            <label for="exampleInputStudyDesc" class="form-label"
              >What institute did you get admitted to in Canada?
            </label>
            <input
              type="text"
              class="form-control"
              placeholder="Your answer"
              name="admit university"
              required
              v-model="admittedUniversityName"
            />
          </div>
          <!-- What is your program of study in Canada? -->
          <div class="mb-3 col-sm-12 col-md-6 col-lg-4">
            <label for="exampleInputStudyDesc" class="form-label"
              >What is your program of study in Canada?
            </label>
            <input
              type="text"
              class="form-control"
              placeholder="Your answer"
              name="program"
              required
              v-model="programName"
            />
          </div>
          <!-- Which country are you applying from? -->
          <div class="mb-3 col-sm-12 col-md-6 col-lg-4">
            <label for="exampleInputStudyDesc" class="form-label"
              >Which country are you applying from?
            </label>
            <input
              type="text"
              class="form-control"
              placeholder="Your answer"
              name="country"
              v-model="yourCountryName"
              required
            />
          </div>
          <!-- What are your future goals? -->
          <div class="mb-3 col-sm-12 col-md-6 col-lg-4">
            <label for="exampleInputStudyDesc" class="form-label"
              >What are your future goals?
            </label>
            <input
              type="text"
              class="form-control"
              placeholder="Your answer"
              name="goal"
              v-model="futureGoals"
              required
            />
          </div>
          <!-- English Scores - Listening -->
          <div class="mb-3 col-sm-12 col-md-6 col-lg-4">
            <label for="exampleInputStudyDesc" class="form-label"
              >English Scores - Listening
            </label>
            <input
              type="text"
              class="form-control"
              placeholder="Your answer"
              name="english scores"
              v-model="listeningScore"
              required
            />
          </div>
          <!-- English Scores - Reading -->
          <div class="mb-3 col-sm-12 col-md-6 col-lg-4">
            <label for="exampleInputStudyDesc" class="form-label"
              >English Scores - Reading
            </label>
            <input
              type="text"
              class="form-control"
              placeholder="Your answer"
              name="reading"
              v-model="readingScore"
              required
            />
          </div>
          <!-- English Scores - Speaking -->
          <div class="mb-3 col-sm-12 col-md-6 col-lg-4">
            <label for="exampleInputStudyDesc" class="form-label"
              >English Scores - Speaking
            </label>
            <input
              type="text"
              class="form-control"
              placeholder="Your answer"
              name="speaking"
              v-model="speakingScore"
              required
            />
          </div>
          <!-- English Scores - writing -->
          <div class="mb-3 col-sm-12 col-md-6 col-lg-4">
            <label for="exampleInputStudyDesc" class="form-label"
              >English Scores - writing
            </label>
            <input
              type="text"
              class="form-control"
              placeholder="Your answer"
              name="writing"
              v-model="writingScore"
              required
            />
          </div>
          <!-- Did you pay your first year tuition? -->
          <div class="mb-3 col-sm-12 col-md-6 col-lg-4">
            <label for="exampleInputStudyDesc" class="form-label"
              >Did you pay your first year tuition?
            </label>
            <div class="form-check">
              <input
                class="form-check-input"
                type="radio"
                name="flexRadio"
                id="flexRadioYes"
                value="Yes"
                v-model="isTutionFeePaid"
              />
              <label class="form-check-label" for="flexRadioYes"> Yes </label>
            </div>
            <div class="form-check">
              <input
                class="form-check-input"
                type="radio"
                name="flexRadio"
                id="flexRadioDefault2"
                checked
                value="No"
                v-model="isTutionFeePaid"
              />
              <label class="form-check-label" for="flexRadioDefault2">
                No
              </label>
            </div>
          </div>
          <!-- How much tuition fee did you pay? -->
          <div class="mb-3 col-sm-12 col-md-6 col-lg-4">
            <label for="exampleInputStudyDesc" class="form-label"
              >How much tuition fee did you pay?
            </label>
            <input
              type="Number"
              class="form-control"
              placeholder="Your answer"
              name="tutionfeepaid"
              required
              v-model="feePaidValue"
            />
          </div>
          <!-- Did you do a GIC? -->
          <div class="mb-3 col-sm-12 col-md-6 col-lg-4">
            <label for="exampleInputGIC" class="form-label"
              >Did you do a GIC?
            </label>
            <div class="form-check">
              <input
                class="form-check-input"
                type="radio"
                name="flexRadioGIC"
                id="flexRadioGIC"
                v-model="isGic"
                value="Yes"
              />
              <label class="form-check-label" for="flexRadioGic2"> Yes </label>
            </div>
            <div class="form-check">
              <input
                class="form-check-input"
                type="radio"
                name="flexRadioGIC"
                id="flexRadioGic2"
                checked
                v-model="isGic"
                value="Yes"
              />
              <label class="form-check-label" for="flexRadioGic2"> No </label>
            </div>
          </div>
          <!-- How much did you pay towards GIC? -->
          <div class="mb-3 col-sm-12 col-md-6 col-lg-4">
            <label for="exampleInputStudyDesc" class="form-label"
              >How much did you pay towards GIC?
            </label>
            <input
              type="text"
              class="form-control"
              placeholder="Your answer"
              name="tutionfeepaid"
              required
              v-model="paidGicValue"
            />
          </div>
        </div>
        <div>
          <button class="btn btn-success" type="submit">Submit</button>
        </div>
      </form>
    </div>
    <div>
      you will receive a mail
      <button
        @click="
          () => {
            isSubmited = false;
          }
        "
      >
        Submit Another response
      </button>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: "HomeView",
  components: {},
  data() {
    return {
      isSubmited: false,
      email: "",
      fullName: "",
      age: null,
      highestEducation: "",
      graduationCollege: "",
      stream: "",
      experience: "",
      admittedUniversityName: "",
      programName: "",
      yourCountryName: "",
      futureGoals: "",
      listeningScore: null,
      readingScore: null,
      speakingScore: null,
      writingScore: null,
      isTutionFeePaid: false,
      feePaidValue: null,
      isGic: false,
      paidGicValue: null,
    };
  },
  methods: {
    Submit() {
      console.log("submit");
      console.log(this.study);
    },
  },
};
</script>
