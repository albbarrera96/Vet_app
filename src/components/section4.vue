<template>
    <section id="#contact" class="bg-white">
        <div class="container-lg my-4 py-4">
          <div class="text-center">
            <h2>CONTACT US</h2>
            <p class="lead">Questions to ask? Fill this form to get in touch with us</p>
          </div>  
          <div class="row justify-content-center my-5">
            <div class="col-lg-6">
              <form>
                <label for="email" class="form-label">Email address:</label>
                <div class="mb-4 input-group">
                  <span class="input-group-text">
                    <i class="bi bi-file-person-fill"></i>
                  </span>
                  <input type="email" class="form-control" id="email" placeholder="email@email.com">
                </div>
                <label for="name" class="form-label">Name:</label>
                <div class="mb-4 input-group">
                  <span class="input-group-text">
                    <i class="bi bi-person-fill"></i>
                  </span>
                  <input type="text" class="form-control" id="name" placeholder="Name">
                </div>
                <label for="subject" class="form-label">What is your question about?</label>
                <div class="mb-4 input-group">
                  <span class="input-group-text">
                    <i class="bi bi-patch-question-fill"></i>
                  </span>
                  <select class="form-select" id="subject">
                    <option value="pricing">Pricing</option>
                    <option value="content">Content</option>
                    <option value="other">Other</option>
                  </select>
                </div>
                <div class="form-floating mb-4 mt-4">
                  <textarea class="form-control" cols="30" rows="10"></textarea>
                  <label for="querry">Write your question...</label>
                </div>
                <div class="mb-4 text-center">
                  <button class="btn btn-secondary btn-lg" type="submit">Submit</button>
                </div>
              </form>
            </div>
          </div>
        </div>
      </section>
</template>

<script>
export default {
    
}
</script>