<template>
    <div class="card flip-container" ontouchstart="this.classList.toggle('hover');">
        <div class="flipper">
            <div class="card-front">
                <div class="card-body">
                    <div class="card-img">

                    </div>
                    <div class="card-info">
                        <h2>1/12/15-1/15/15</h2>
                        <h2>$5</h2>
                    </div>
                </div>
            </div>
            <div class="card-back">
                <div class="card-detail">
                    <h2>Eric Clinger</h2>
                    <h2>2082012346</h2>
                    <h2>cling4@byu.edu</h2>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default { 
    
};
</script>

<style lang="scss" scoped>
    /* entire container, keeps perspective */
    .flip-container {
        perspective: 1000px;
    }
        /* flip the pane when hovered */
        .flip-container:hover .flipper, .flip-container.hover .flipper {
            transform: rotateY(180deg);
        }

    .flip-container, .card-front, .card-back {
        width: 480px;
        height: 320px;
    }

    /* flip speed goes here */
    .flipper {
        transition: 0.6s;
        transform-style: preserve-3d;
        position: relative;
    }

    /* hide back of pane during swap */
    .card-front, .card-back {
        backface-visibility: hidden;
        position: absolute;
        top: 0;
        left: 0;
    }

    /* front pane, placed above back */
    .card-front {
        z-index: 2;
        /* for firefox 31 */
        transform: rotateY(0deg);
    }

    /* back, initially hidden pane */
    .card-back {
        transform: rotateY(180deg);
    }

.card-front, .card-back {
    margin: 1rem;
    border-radius: 10px; 
    box-shadow: 5px 10px 8px #888888;
}

.card-body {
    line-height: 50%;
}

.card-body h5 {
    font-weight: bold;
}
.card-img {
    width: 100%;
    text-align: center;
    border-radius: 10px;
}

html, body {
    max-width: 100%;
    overflow-x: hidden;
}

body {
    padding-bottom: 10rem;
}
</style>