<template>
  <div class="about">
    <div id="root" />
  </div>
</template>
<script>
import anime from 'animejs'
export default {
  name:'About',
  data  (){
    return{
    }
  },
  mounted(){
    class App extends React.Component {
      handleMouseMove = (e) => {
        const el = document.getElementById("wrapper");
        const d = el.getBoundingClientRect();
        let x = e.clientX - (d.left + Math.floor(d.width / 2));
        let y = e.clientY - (d.top + Math.floor(d.height / 2));
        // Invert values
        x = x - x * 2;
        y = y - y * 2;
        document.documentElement.style.setProperty("--scale", 1.6);
        document.documentElement.style.setProperty("--x", x / 2 + "px");

        document.documentElement.style.setProperty("--y", y / 2 + "px");
      };

      handleMouseLeave = () => {
        document.documentElement.style.setProperty("--scale", 1);
        document.documentElement.style.setProperty("--x", 0);
        document.documentElement.style.setProperty("--y", 0);
      };
      render() {
        return (
            <div id="wrapper" onMouseMove={this.handleMouseMove} onClick={this.handleMouseLeave}>
              <img id="image" />
            </div>
        );
      }
    }

    ReactDOM.render(<App />, document.getElementById("root"));

  }
}
</script>
<style lang="scss">
.about {
  height: 100vh;
  background-color: #35dad2;
  display: flex;
  justify-content: center;
  align-items: center;
  align-content: center;
}
:root {
  --scale: 1.5;
  --y: 0;
  body {
    margin: 0;
    background-color: black;
    outline: none;
    border: none;
    #wrapper {
      width: 100vw;
      height: 100vh;
      #image {
        width: 100vw;
        height: 100vh;
        background-image: url("https://images.unsplash.com/photo-1539035104074-dee66086b5e3?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjI0MX0&auto=format&fit=crop&w=2550&q=80");
        background-size: cover;
        transform: translateX(var(--x)) translateY(var(--y)) scale(var(--scale));
        transition: ease-out 0.7s;

      }
    }
  }
}
</style>
