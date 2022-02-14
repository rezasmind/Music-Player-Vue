<template>
    <div class="container">
        <div class="cover">
            <img src="../../Image1.png" alt="" srcset="">

            <div class="info" >
                <h1>{{ title }}</h1>
                <h2>{{ artist }}</h2>
            </div>
        </div>

        <div class="bar">
            <div class="progress">
                <div class="progress-container" id="progress-container">
                    <div class="progress" id="progress"></div>
                    <audio src="http://dl.tehsong.xyz/tehsong/Hosein/1400/Mehr/Persian-Music/09/Ezza%20-%20TELL%20ME%20THE%20PRICE%20(Ft%20Mamazi)%20(128).mp3" id="audio"></audio>
                            <div class="navigation">
                                <button id="prev" class="action-btn">
                                    <i class="fas fa-backward"></i>
                                </button>
                                <button id="play" class="action-btn action-btn-big">
                                    <i class="fas fa-play"></i>
                                </button>
                                <button id="next" class="action-btn">
                                    <i class="fas fa-forward"></i>
                                </button>
                            </div>
                </div>
            </div>
        </div>

    </div>
</template>

<script>


export default {
    name: 'Music',
    setup() {
        return {
            title: "Sarbaz",
            artist: "Mamazi"
        }
    },
    created: function() {
        this.audio.addEventListener("loadedmetadata", function() {
            progressContainer.style.width = audio.duration + "px";
        });

        this.audio.addEventListener("timeupdate", function() {
            var percent = audio.currentTime / audio.duration;
            progress.style.width = percent * progressContainer.offsetWidth + "px";
        });

        this.play.addEventListener("click", function() {
            if (this.audio.paused) {
                this.audio.play();
                this.play.innerHTML = '<i class="fas fa-pause"></i>';
            } else {
                this.audio.pause();
                this.play.innerHTML = '<i class="fas fa-play"></i>';
            }
        });

    },
  }

    var progress = document.getElementById("progress");
    var progressContainer = document.getElementById("progress-container");
    var audio = document.getElementById("audio");
    var play = document.getElementById("play");




</script>

<style>
  .action-btn {
    background-color: #000;
    border: 0;
    color: white;
    border-radius: 50%;
    font-size: 15px;
    cursor: pointer;
    padding: 15px;
    margin: 7px;
  }


  .action-btn.action-btn-big {
    color: white;
    font-size: 30px;
  }

  .action-btn:focus {
    outline: 0;
  }

.container {
    background: black;
    width: 100%;
    height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

h1,h2,h3,p,span {
    margin: 15px;
    padding: 0px;
    color: white;
}

.cover {

    border: 1px solid black;
    border-radius: 48px;
}

.cover img {
    width: 400px;
    border-radius: 48px;
}

.bar {
    position: absolute;
    bottom: 0px;
    background: rgb(44, 44, 44);
    width: 100%;
    height: 10%;
    display: flex;
    flex-direction: row;
    align-items: center;

}
.navigation {
    margin-left: 15px;
}

.progress {
    background-color: white;
    border-radius: 5px;
    height: 100%;
    width: 50%;
    transition: width 0.1s linear;
}
</style>
