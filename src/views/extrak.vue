<template>

    <div class="extrak_hatter"
    :style="{
      'background-image': `url(${require('../assets/images/extrak_background.jpeg')})`,
    }">

    <div class="page " style="position: relative;"> 

        <div class="logo_container">

            <div class="container">

            <h1 class="display-1 white" style="color: whitesmoke;">Extra</h1>
            <h1 class="display-2 white" style="color: whitesmoke;">szolgáltatások</h1>

            <div class="row">

                <div class="col lg-auto extra_img">
                     <button type="button" class="btn btn-link" data-toggle="modal" data-target="#ModalBicikli"><img src="../assets/images/button_bike.png"></button>
                </div>

                <div class="col lg-auto extra_img">
                    <button type="button" class="btn btn-link" data-toggle="modal" data-target="#ModalBoatCentered"><img src="../assets/images/button_boat.png"></button>
                </div>

                <div class="col lg-auto extra_img">
                    <button type="button" class="btn btn-link" data-toggle="modal" data-target="#ModalBath"><img src="../assets/images/button_bath.png"></button>
                </div>

            </div>

            </div>

        </div>

    </div>


        <!-- Modal Bicikli -->
        <div class="modal fade extrakModal" id="ModalBicikli" tabindex="-1" role="dialog" aria-labelledby="exampleModalCenterTitle" aria-hidden="true">
        <div class="modal-dialog modal-dialog-centered" role="document">
            <div class="modal-content">
            <div class="modal-header">
                <h5 class="display-5" id="exampleModalLongTitle">Bicikli bérlés</h5>
                <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                <span aria-hidden="true">&times;</span>
                </button>
            </div>
            <div class="display-6">
                Vendégházunkban lehetőségetek van biciklit bérelni, 4 normál és egy elektromos bicikli közül választhattok. A bicikli a legjobb közlekedési eszköz a Balaton környékén, a szomszédos falvakon át gyönyörű helyekre látogathattok el, sok étterem, kávézó elérhető így.
            </div>
            </div>
        </div>
        </div>


        <!-- Modal Boat -->
        <div class="modal fade extrakModal" id="ModalBoatCentered" tabindex="-1" role="dialog" aria-labelledby="exampleModalCenterTitle" aria-hidden="true">
        <div class="modal-dialog modal-dialog-centered" role="document">
            <div class="modal-content">
            <div class="modal-header">
                <h5 class="display-5" id="exampleModalLongTitle">Vitorlázás</h5>
                <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                <span aria-hidden="true">&times;</span>
                </button>
            </div>
            <div class="display-6">
                Ha szeretnétek és az időjárás is engedi, egy kedves kapitány barátunk szívesen lát Titeket a Balatonon a vitorláshajóján. Jelentkezni nála lehet, a 0670/1234567 számon.
            </div>
            </div>
        </div>
        </div>


        <!-- Modal Bath -->
        <div class="modal fade extrakModal" id="ModalBath" tabindex="-1" role="dialog" aria-labelledby="exampleModalCenterTitle" aria-hidden="true">
        <div class="modal-dialog modal-dialog-centered" role="document">
            <div class="modal-content">
            <div class="modal-header">
                <h5 class="display-5" id="exampleModalLongTitle">Dézsa</h5>
                <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                <span aria-hidden="true">&times;</span>
                </button>
            </div>
            <div class="display-6">
                Kertünkben kétszemélyes dézsa várja a feltöltődni vágyókat. Hideg időben kellemes időtöltés kirándulás után, előtt vagy helyett.
            </div>
            </div>
        </div>
        </div>

    </div>

</template>

<script>
export default {
    name: "Extrak"
}
</script>