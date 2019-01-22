<template>
    <form action="">

         <hr/>
        <h2>Submit</h2>
       
        <form>
            <div class="form-group">
                <label for="exampleFormControlFile1">Upload Logo</label>
                <input @change="placeLogo" type="file" class="form-control-file" id="logoImg">

                  <div class="form-group">
                    <label for="exampleInputEmail1">Title</label>
                    <input v-model="title.title" type="text" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp" placeholder="Title">
                    <input v-model="title.author" type="text" class="form-control" id="examplejçhttp://localhost:5000InputEmail1" aria-describedby="emailHelp" placeholder="Title">
                </div>
                <button v-on:click.prevent.stop="createImage">image</button>
                <button v-on:click.prevent.stop="dlImage">image</button>
               
            </div>
        </form>
    </form>
</template>

<script>
export default {
    name:"BookForm",
    props: ["title"],
  
    methods: {
        placeLogo(e) {

            var url = URL.createObjectURL(e.target.files[0]);

            $("#logo").attr("src",url);
        },
        createImage(e) {
          
            var book = $("#tridiv").get(0);

            var html2canvasOptions ={
    
                foreignObjectRendering:true,
                useCORS:true,
                allowTaint:true,
                proxy:"https://crossorigin.me",
                scrollY:100,
                y:10,
                width:600,
                height:400
                

            };

              html2canvas(book,html2canvasOptions).then(function(canvas,html2canvasOption){

                //Canvas2Image.saveAsImage(canvas, 400, 600, "png", "test");

                var theCanvas = canvas;
                document.body.appendChild(theCanvas);

                // Convert and download as image 
                Canvas2Image.saveAsPNG(theCanvas,1000,1000); 

 
            })

            
        }
    }
};
</script>
