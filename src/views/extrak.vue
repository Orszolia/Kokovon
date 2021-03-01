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

                <div class="col">
                    <img src="../assets/images/button_bike.png">
                </div>

                <div class="col">
                    <img src="../assets/images/button_boat.png">
                </div>

                <div class="col">
                    <img src="../assets/images/button_bath.png">
                </div>

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