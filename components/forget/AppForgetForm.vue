<template>
    <div class="user-area pt-100 pb-70">
        <div class="container">
            <div class="user-form forget">
                <div class="contact-form">
                    <h2>Forget Password</h2>
                    <form>
                        <div class="row">
                            <div class="col-lg-12 ">
                                <div class="form-group">
                                    <input type="text" class="form-control" required="" data-error="Please enter username or email" placeholder="Username or Email">
                                </div>
                            </div>
                            <div class="col-lg-12 ">
                                <button type="submit" class="default-btn btn-bg-two">
                                    Reset Now
                                </button>
                            </div>
                        </div>
                    </form>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {

}
</script>

<style>
.user-form.forget .contact-form {
  max-width: 640px;
  margin: 0 auto;
}
</style>