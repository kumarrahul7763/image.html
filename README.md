<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<body>
    <script src="https://cdn.jsdelivr.net/npm/axios@1.6.7/dist/axios.min.js"></script>
    <h1>Get random image</h1>
    <button>Show </button>
    <img id="result">
    <script src="image.js">
      let btn = document.querySelector("button");
let url2 = "https://dog.ceo/api/breeds/image/random";
btn.addEventListener("click", async() => {
    let link = await getImage();
    //console.log(link);
    let img = document.querySelector("#result");
    img.setAttribute("src", link);
    console.log(link);
});
async function getImage() {
    try {
        let res = await axios.get(url2);
        return res.data.message;
    } catch (e) {
        console.log("error -", e);
        return "/";
    }
}
    </script>
</body>

</html>
