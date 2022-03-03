<template>
        <div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title" id="exampleModalLabel">Человек-паук</h5>
            <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
          </div>
          <div class="modal-body">
            <img src="https://vgtimes.ru/uploads/posts/2021-10/82020_1_1.jpg" class="img-fluid rounded-start" alt="poster">
            <div>
              <h5>Описание</h5>
              <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Architecto a tempore nobis possimus rerum
                molestias, natus expedita quibusdam praesentium. Incidunt ullam reprehenderit in ut dolorem vitae illum
                porro, laboriosam exercitationem.</p>
              <h5>Комиксы</h5>
              <ul>
                <li>Adventures of Spider-Man (1996) #1</li>
                <li>Adventures of Spider-Man (1996) #2</li>
                <li>Adventures of Spider-Man (1996) #3</li>
              </ul>
            </div>
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Закрыть</button>
          </div>
        </div>
      </div>
    </div>
</template>

<script>
    export default {
        name: "AppModal",
    }
</script>

<style scoped>

</style>
