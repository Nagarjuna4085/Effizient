<template>
  <div class="">
    <p>{{ isTutionFeePaid }}</p>
    <div v-if="!isSubmited" class="container">
      <h1>Customized SOP Generator</h1>
      <!-- <button @click="Submit">send</button> -->
      <form action="javascript:;" @submit="Submit()">
        <div class="row">
          <!-- //email -->
          <div class="mb-3 col-sm-12 col-md-6 col-lg-4">
            <label for="exampleInputEmail1" class="form-label"
              >Email <span class="require">*</span>
            </label>
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
            <label for="exampleInputName" class="form-label"
              >Full Name <span class="require">*</span></label
            >

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
            <label for="exampleInputAge" class="form-label"
              >Age <span class="require">*</span></label
            >
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
              >Highest Level of Education <span class="require">*</span></label
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
              >Institute where you completed your highest level of education
              <span class="require">*</span></label
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
              >What did you study <span class="require">*</span>
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
              yes: <span class="require">*</span><br />
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
              <span class="require">*</span>
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
              <span class="require">*</span>
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
              <span class="require">*</span>
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
              >What are your future goals? <span class="require">*</span>
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
              >English Scores - Listening <span class="require">*</span>
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
              >English Scores - Reading <span class="require">*</span>
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
              >English Scores - Speaking <span class="require">*</span>
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
              >English Scores - writing <span class="require">*</span>
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
              <span class="require">*</span>
            </label>
            <div class="form-check">
              <input
                class="form-check-input"
                type="radio"
                name="flexRadio"
                id="flexRadioYes"
                value="true"
                v-model="isTutionFeePaid"
              />
              <label class="form-check-label" for="flexRadioYes"> Yes </label>
            </div>
            <div class="form-check">
              <input
                class="form-check-input"
                type="radio"
                name="flexRadio1"
                id="flexRadioDefault2"
                value="false"
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
              >How much tuition fee did you pay? <span class="require">*</span>
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
              >Did you do a GIC? <span class="require">*</span>
            </label>
            <div class="form-check">
              <input
                class="form-check-input"
                type="radio"
                name="flexRadioGIC"
                id="flexRadioGIC"
                v-model="isGic"
                value="true"
              />
              <label class="form-check-label" for="flexRadioGic2"> Yes </label>
            </div>
            <div class="form-check">
              <input
                class="form-check-input"
                type="radio"
                name="flexRadioGIC2"
                id="flexRadioGic2"
                v-model="isGic"
                value="false"
              />
              <label class="form-check-label" for="flexRadioGic2"> No </label>
            </div>
          </div>
          <!-- How much did you pay towards GIC? -->
          <div class="mb-3 col-sm-12 col-md-6 col-lg-4">
            <label for="exampleInputStudyDesc" class="form-label"
              >How much did you pay towards GIC? <span class="require">*</span>
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
          <button class="btn btn-success" type="submit">
            <div v-if="loader">
              <div class="spinner-border" role="status">
                <span class="visually-hidden">Loading...</span>
              </div>
            </div>
            <div v-else>Submit</div>
          </button>
        </div>
      </form>
    </div>
    <div class="container d-flex justify-content-center mb-3" v-if="isSubmited">
      <div class="card" style="width: 18rem">
        <img
          class="card-img-top"
          src="../assets/image.png"
          alt="Card image cap"
        />
        <div class="card-body">
          <h5 class="card-title">Response Stored</h5>
          <p class="card-text">
            You will receive your attachment to your mail shortly
          </p>
          <button
            class="btn btn-primary"
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
    </div>
  </div>
</template>

<script>
import axios from "axios";
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: "HomeView",
  components: {},
  data() {
    return {
      loader: false,
      isSubmited: false,
      email: "snagarjuna2001@gmail.com",
      fullName: "Nagarjuna",
      age: 23,
      highestEducation: "Bachelors Degree",
      graduationCollege: "JNTUA",
      stream: "computer science",
      experience: "in web development",
      admittedUniversityName: "toronto university",
      programName: "masters in artificial intellegence",
      yourCountryName: "India",
      futureGoals: "full stack developer",
      listeningScore: 7,
      readingScore: 7,
      speakingScore: 7,
      writingScore: 7,
      isTutionFeePaid: null,
      feePaidValue: 2000,
      isGic: null,
      paidGicValue: 5000,
    };
  },
  methods: {
    Submit() {
      this.loader = true;
      console.log("submit");
      const data = {
        email: this.email,
        fullName: this.fullName,
        age: this.age,
        highestEducation: this.highestEducation,
        graduationCollege: this.graduationCollege,
        stream: this.stream,
        experience: this.email,
        admittedUniversityName: this.admittedUniversityName,
        programName: this.programName,
        yourCountryName: this.yourCountryName,
        futureGoals: this.futureGoals,
        listeningScore: this.listeningScore,
        readingScore: this.readingScore,
        speakingScore: this.speakingScore,
        writingScore: this.writingScore,
        isTutionFeePaid: this.isTutionFeePaid,
        feePaidValue: this.feePaidValue,
        isGic: this.isGic,
        paidGicValue: this.paidGicValue,
      };
      // https://effizient-backend-app.onrender.com
      try {
        axios
          .post("https://effizient-backend-app.onrender.com/sendformdata", {
            data,
          })
          .then((response) => {
            this.loader = false;
            console.log(response);
            this.isSubmited = true;
            this.email = "";
            this.fullName = "";
            this.age = null;
            this.highestEducation = "";
            this.graduationCollege = "";
            this.stream = "";
            this.experience = "";
            (this.admittedUniversityName = ""), (this.programName = "");
            (this.yourCountryName = ""),
              (this.futureGoals = ""),
              (this.readingScore = ""),
              (this.speakingScore = ""),
              (this.writingScore = ""),
              (this.listeningScore = ""),
              (this.isTutionFeePaid = ""),
              (this.feePaidValue = ""),
              (this.isGic = ""),
              (this.paidGicValue = "");
          });
      } catch (error) {
        console.log(error);
        this.loader = false;
      }
    },
  },
};
</script>
<style>
form {
  border-radius: 5px;
  background-color: #f2f2f2;
  padding: 20px;
}
label {
  font-weight: bold;
}
.require {
  color: red;
}
</style>
