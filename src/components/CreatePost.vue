function createPost() {

  let imageUrl = null

  if (file.value) {
    imageUrl = URL.createObjectURL(file.value)
  }

  posts.value.unshift({
    text: text.value,
    image: imageUrl
  })

  text.value = ''
  file.value = null
  preview.value = null

}