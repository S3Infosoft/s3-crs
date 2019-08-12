<template>
    <div class="container">

        <div class="card o-hidden border-0 shadow-lg my-5">
        <div class="card-body p-0">
            <!-- Nested Row within Card Body -->
            <div class="row">
            <div class="col-lg-5 d-none d-lg-block bg-register-image"></div>
            <div class="col-lg-7">
                <div class="p-5">
                <div class="text-center">
                    <h1 class="h4 text-gray-900 mb-4">Create an Account!</h1>
                </div>
                <form class="user">
                    <div class="form-group row">
                    <div class="col-sm-6 mb-3 mb-sm-0">
                        <input v-model="name" type="text" class="form-control form-control-user" id="exampleFirstName" placeholder="Name of Hotel">
                    </div>
                    <div class="col-sm-6">
                        <input v-model="organisation" type="text" class="form-control form-control-user" id="exampleLastName" placeholder="Name of Organisation">
                    </div>
                    </div>
                    <div class="form-group">
                    <input v-model="email" type="email" class="form-control form-control-user" id="exampleInputEmail" placeholder="Email Address">
                    </div>
                    <div class="form-group row">
                    <div class="col-sm-6 mb-3 mb-sm-0">
                        <input v-model="password" type="password" class="form-control form-control-user" id="exampleInputPassword" placeholder="Create Password">
                    </div>
                    </div>
                    <hr>
                    <div class="col-sm-6 mt-3">
                        <h5><b>Hotel Details</b></h5>
					<b>Image One</b><input type="file" name="image" class="form-control-file">
                    <b>Image Two</b><input type="file" name="image" class="form-control-file">
				</div><br>
                <div class="form-group row">
                    <div class="col-sm-6 mb-3 mb-sm-0">
                        <input v-model="city" type="text" class="form-control form-control-user" id="exampleCity" placeholder="City">
                    </div>
                    <div class="col-sm-6">
                        <input v-model="state" type="text" class="form-control form-control-user" id="exampleState" placeholder="State">
                    </div>
                    </div>
                    <div class="form-group row">
                    <div class="col-sm-6 mb-3 mb-sm-0">
                        <input v-model="zip" type="numbers" class="form-control form-control-user" id="exampleZIP" placeholder="ZIP">
                    </div>
                    <div class="col-sm-6">
                        <input v-model="country" type="text" class="form-control form-control-user" id="exampleCountry" placeholder="Country">
                    </div>
                    </div>
                    <div class="form-group row">
                    <div class="col-sm-6 mb-3 mb-sm-0">
                        <input v-model="currency" type="text" class="form-control form-control-user" id="exampleCurrency" placeholder="Currency Preference">
                    </div>
                    </div>
                <div class="form-group">
                    <textarea v-model="address" rows="2" class="form-control form-control-user" id="Exampleaddress" placeholder="Address"></textarea>
                    </div>
                    <div class="form-group">
                    <textarea v-model="description" rows="3" class="form-control form-control-user" id="Exampledescription" placeholder="Description"></textarea>
                    </div>
                    <hr>
                    <div class="col-sm-6 mt-3">
                        <h5><b>Additional Images</b></h5>
					<b>Image Three</b><input type="file" name="image" class="form-control-file">
                    <b>Image Four</b><input type="file" name="image" class="form-control-file">
				</div><br>
                <hr>
                <h4>Hotel Policy Section</h4>
                <div class="form-group row">
                    <div class="col-sm-6 mb-3 mb-sm-0">
                        <input v-model="outtime" type="numbers" class="form-control form-control-user" id="examplein" placeholder="Check out Time">
                    </div>
                    <div class="col-sm-6">
                        <input v-model="intime" type="text" class="form-control form-control-user" id="exampleOut" placeholder="Check in Time">
                    </div>
                    </div>
                    <b><h6>Late Checkout allowed</h6></b>
                    <div>
                    <input type="radio" id="exampleYes" name="Yes" value="yes">
                    <label for="Yes">Yes</label>
                    </div>
                    <div>
                    <input type="radio" id="exampleNo" name="No" value="no">
                    <label for="No">No</label>
                    </div>
                    <div class="form-group row">
                    <div class="col-sm-6 mb-3 mb-sm-0">
                        <input v-model="outtype" type="text" class="form-control form-control-user" id="exampleType" placeholder="Checkout Type">
                    </div>
                    <div class="col-sm-6">
                        <input v-model="outvalue" type="numbers" class="form-control form-control-user" id="exampleValue" placeholder="Checkout Value">
                    </div>
                    </div>
                    <div class="form-group">
                    <textarea v-model="terms" rows="4" class="form-control form-control-user" id="exampleTerms" placeholder="Terms and Conditions"></textarea>
                    </div>
                    <hr>
                    <a @click="registerUser()" href="" class="btn btn-primary btn-user btn-block">
                    <router-link class="nav-link" to="/login">Register Hotel</router-link>
                    </a>
                </form>
                <hr>
                <div class="text-center">
                    <a class="small" href="forgot-password.html">Forgot Password?</a>
                </div>
                <div class="text-center">
                    <a class="small" href="login.html">Already have an account? Login!</a>
                </div>
                </div>
            </div>
            </div>
        </div>
        </div>

    </div>
</template>

<script>
import Axios from 'axios';
export default {
    data(){
        return{
            name:'',
            organisation:'',
            email:'',
            password:'',
            city:'',
            state:'',
            zip:'',
            country:'',
            currency:'',
            address:'',
            description:'',
            outtime:'',
            intime:'',
            outtype:'',
            outvalue:'',
            terms:''
        }
    },
    methods:{
        registerUser(){
            Axios.post('https://hotels.s3infosoft.com/api/v1/getHotelDetails/auth/register', {
                name: this.name,
                organisation: this.organisation,
                email: this.email,
                password: this.password,
                city: this.city,
                state: this.state,
                zip: this.zip,
                country: this.country,
                currency: this.currency,
                address: this.address,
                description: this.description,
                outtime: this.outtime,
                intime: this.intime,
                outtype: this.outtype,
                outvalue: this.outvalue,
                terms: this.terms
            }).then(response => {
                console.log(response)
            }).catch(error => {
                console.log(error)
            })
        }
    }
}
</script>
