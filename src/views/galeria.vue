<template>

    <div class="container">
        <div class="container page bemutatkozas">
            <h1 class="display-1">Nézz körül a</h1>
            <h1 class="display-2">vendégházban</h1>
      
            <div class="row">

                <div class="col">
                    <button type="button" class="btn btn-link" data-toggle="modal" data-target="#exampleModalLong">
                    <img 
                    class="galeria house"
                    src="../assets/images/galeria_house.png" style="width: 450px;">
                    </button>
                </div>
                
                <div class="col">
                    <img 
                    class="galeria lake"
                    src="../assets/images/galeria_lake.png" style="width: 450px;">
                </div>

            </div>

            <div class="row">

                <div class="col">                    
                    <img 
                    class="galeria road1"
                    src="../assets/images/road_1.png" style="width: 160px;">
                </div>
                
                <div class="col">
                    <img 
                    class="galeria pajta"
                    src="../assets/images/galeria_pajta.png" style="width: 450px;">
                </div>

                <div class="col">
                    <img 
                    class="galeria road2"
                    src="../assets/images/road_2.png" style="width: 140px;">
                </div>

            </div>
            

        </div>

        <!-- Button trigger modal -->

            <!-- Modal -->
            <div class="modal fade" id="exampleModalLong" tabindex="-1" role="dialog" aria-labelledby="exampleModalLongTitle" aria-hidden="true">
            <div class="modal-dialog-apartman" role="document"> 
                <div class="modal-content" >
                <div class="modal-header">
                    <h5 class="modal-title" id="exampleModalLongTitle">Modal title</h5>
                    <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                    <span aria-hidden="true">&times;</span>
                    </button>
                </div>
                <div class="modal-body" >

                    <div class="row_galeria">

                        <div class="column galeria1">
                            <img src="../assets/images/galeria/house1.jpeg">
                            <img src="../assets/images/galeria/house2.jpeg">
                            <img src="../assets/images/galeria/terasz1.jpg">
                            <img src="../assets/images/galeria/sirdavid6.jpg">
                            <img src="nature.jpg">
                            <img src="mist.jpg">
                            <img src="paris.jpg">
                        </div>

                        <div class="column galeria2">
                            <img src="../assets/images/galeria/bird2.jpeg">
                            <img src="../assets/images/galeria/terasz.jpeg">
                            <img src="../assets/images/galeria/terasz2.jpg">
                            <img src="../assets/images/galeria/sirdavid7.jpg">
                            <img src="rocks.jpg">
                            <img src="underwater.jpg">
                        </div>

                        <div class="column galeria3">
                            <img src="../assets/images/galeria/lamp.jpeg">
                            <img src="../assets/images/galeria/winter1.png">
                            <img src="../assets/images/galeria/terasz3.jpg">
                            <img src="../assets/images/galeria/sirdavid8.jpg">
                            <img src="nature.jpg">
                            <img src="mist.jpg">
                            <img src="paris.jpg">
                        </div>

                    </div>
                </div>

                </div>
            </div>
            </div>

    </div>

</template>