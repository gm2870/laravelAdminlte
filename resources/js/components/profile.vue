<template>
    <div class="container">
        <div class="row mt-3">
            <div class="col-md-12">
                <!-- Widget: user widget style 1 -->
                <div class="card card-widget widget-user">
                    <!-- Add the bg color to the header using any of the bg-* classes -->
                    <div
                        class="widget-user-header text-white"
                        style="background-image:url('/images/photo1.png');background-position:center;height: 250px;"
                    >
                        <h3 class="widget-user-username text-right">Elizabeth Pierce</h3>
                        <h5 class="widget-user-desc text-right">Web Designer</h5>
                    </div>
                    <div class="widget-user-image">
                        <img class="img-circle" :src="getProfilePhoto()" alt="User Avatar" />
                    </div>
                    <div class="card-footer pt-3">
                        <div class="row">
                            <div class="col-sm-4 border-right">
                                <div class="description-block">
                                    <h5 class="description-header">3,200</h5>
                                    <span class="description-text">SALES</span>
                                </div>
                                <!-- /.description-block -->
                            </div>
                            <!-- /.col -->
                            <div class="col-sm-4 border-right">
                                <div class="description-block">
                                    <h5 class="description-header">13,000</h5>
                                    <span class="description-text">FOLLOWERS</span>
                                </div>
                                <!-- /.description-block -->
                            </div>
                            <!-- /.col -->
                            <div class="col-sm-4">
                                <div class="description-block">
                                    <h5 class="description-header">35</h5>
                                    <span class="description-text">PRODUCTS</span>
                                </div>
                                <!-- /.description-block -->
                            </div>
                            <!-- /.col -->
                        </div>
                        <!-- /.row -->
                    </div>
                </div>
                <!-- /.widget-user -->
            </div>
        </div>
        <div class="row">
            <div class="col-md-12">
                <div class="card">
                    <div class="card-header p-2">
                        <ul class="nav nav-pills">
                            <li class="nav-item">
                                <a class="nav-link" href="#activity" data-toggle="tab">Activity</a>
                            </li>
                            <li class="nav-item">
                                <a
                                    class="nav-link active"
                                    href="#settings"
                                    data-toggle="tab"
                                >Settings</a>
                            </li>
                        </ul>
                    </div>
                    <div class="card-body">
                        <div class="tab-content">
                            <div class="tab-pane active" id="settings">
                                <form class="form-horizontal">
                                    <div class="form-group row">
                                        <label for="inputName" class="col-sm-2 col-form-label">Name</label>
                                        <div class="col-sm-10">
                                            <input
                                                v-model="form.name"
                                                type="email"
                                                class="form-control"
                                                id="inputName"
                                                placeholder="Name"
                                                :class="{ 'is-invalid': form.errors.has('name') }"
                                            />
                                            <has-error :form="form" field="name"></has-error>
                                        </div>
                                    </div>
                                    <div class="form-group row">
                                        <label
                                            for="inputEmail"
                                            class="col-sm-2 col-form-label"
                                        >Email</label>
                                        <div class="col-sm-10">
                                            <input
                                                v-model="form.email"
                                                type="email"
                                                class="form-control"
                                                id="inputEmail"
                                                placeholder="Email"
                                                :class="{ 'is-invalid': form.errors.has('email') }"
                                            />
                                            <has-error :form="form" field="email"></has-error>
                                        </div>
                                    </div>
                                    <div class="form-group row">
                                        <label
                                            for="inputPassword"
                                            class="col-sm-2 col-form-label"
                                        >Password</label>
                                        <div class="col-sm-10">
                                            <input
                                                v-model="form.password"
                                                type="password"
                                                class="form-control"
                                                id="inputPassword"
                                                placeholder="Password"
                                                :class="{ 'is-invalid': form.errors.has('password') }"
                                            />
                                            <has-error :form="form" field="password"></has-error>
                                        </div>
                                    </div>
                                    <div class="form-group row">
                                        <label
                                            for="inputExperience"
                                            class="col-sm-2 col-form-label"
                                        >Experience</label>
                                        <div class="col-sm-10">
                                            <textarea
                                                class="form-control"
                                                id="inputExperience"
                                                placeholder="Experience"
                                            ></textarea>
                                        </div>
                                    </div>
                                    <div class="form-group row">
                                        <label
                                            for="inputSkills"
                                            class="col-sm-2 col-form-label"
                                        >Profile Photo</label>
                                        <div class="col-sm-10">
                                            <input @change="updateProfilePhoto" type="file" />
                                        </div>
                                    </div>
                                    <div class="form-group row">
                                        <div class="offset-sm-2 col-sm-10">
                                            <div class="checkbox">
                                                <label>
                                                    <input type="checkbox" /> I agree to the
                                                    <a href="#">terms and conditions</a>
                                                </label>
                                            </div>
                                        </div>
                                    </div>
                                    <div class="form-group row">
                                        <div class="offset-sm-2 col-sm-10">
                                            <button
                                                type="submit"
                                                @click.prevent="updateProfile"
                                                class="btn btn-danger"
                                            >Submit</button>
                                        </div>
                                    </div>
                                </form>
                            </div>
                            <div class="tab-pane" id="activity">
                                <div class="post">
                                    <div class="user-block">
                                        <img
                                            class="img-circle img-bordered-sm"
                                            src="/images/user1-128x128.jpg"
                                            alt="user image"
                                        />
                                        <span class="username">
                                            <a href="#">Jonathan Burke Jr.</a>
                                            <a href="#" class="float-right btn-tool">
                                                <i class="fas fa-times"></i>
                                            </a>
                                        </span>
                                        <span class="description">Shared publicly - 7:30 PM today</span>
                                    </div>
                                    <!-- /.user-block -->
                                    <p>
                                        Lorem ipsum represents a long-held tradition for designers,
                                        typographers and the like. Some people hate it and argue for
                                        its demise, but others ignore the hate as they create awesome
                                        tools to help create filler text for everyone from bacon lovers
                                        to Charlie Sheen fans.
                                    </p>
                                    <p>
                                        <a href="#" class="link-black text-sm mr-2">
                                            <i class="fas fa-share mr-1"></i> Share
                                        </a>
                                        <a href="#" class="link-black text-sm">
                                            <i class="far fa-thumbs-up mr-1"></i> Like
                                        </a>
                                        <span class="float-right">
                                            <a href="#" class="link-black text-sm">
                                                <i class="far fa-comments mr-1"></i> Comments (5)
                                            </a>
                                        </span>
                                    </p>
                                    <input
                                        class="form-control form-control-sm"
                                        type="text"
                                        placeholder="Type a comment"
                                    />
                                </div>
                                <!-- tab-pane -->
                            </div>
                            <!-- post -->
                        </div>
                        <!-- tab-content -->
                    </div>
                    <!-- card-body -->
                </div>
                <!-- card -->
            </div>
            <!-- col-md-12 -->
        </div>
        <!-- row -->
    </div>
</template>

<script>
export default {
    data() {
        return {
            form: new Form({
                id: "",
                name: "",
                email: "",
                password: "",
                type: "",
                bio: "",
                photo: ""
            })
        };
    },
    methods: {
        getProfilePhoto() {
            let prefix = this.form.photo.match(/\//) ? "" : "/images/profile/";
            return prefix + this.form.photo;
        },
        updateProfile() {
            this.$Progress.start();
            if (this.form.password == "") {
                this.form.password = undefined;
            }
            this.form
                .put("api/profile")
                .then(() => {
                    this.$Progress.finish();
                })
                .catch(() => {
                    this.$Progress.fail();
                });
        },
        updateProfilePhoto(e) {
            let file = e.target.files[0];
            console.log(file);
            if (file["size"] < 2111775) {
                let reader = new FileReader();
                reader.onloadend = file => {
                    this.form.photo = reader.result;
                };
                reader.readAsDataURL(file);
            } else {
                this.form.photo = "";
                Swal.fire({
                    type: "error",
                    title: "oops...",
                    text: "image size should be less than 2mb"
                });
            }
        }
    },
    created() {
        axios.get("api/profile").then(({ data }) => {
            this.form.fill(data);
        });
    }
};
</script>
