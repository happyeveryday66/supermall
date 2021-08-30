<template>
  <div class="wrapper">
    <ul class="content">
      <li>分类的列表1</li>
      <li>分类的列表2</li>
      <li>分类的列表3</li>
      <li>分类的列表4</li>
      <li>分类的列表5</li>
      <li>分类的列表6</li>
      <li>分类的列表7</li>
      <li>分类的列表8</li>
      <li>分类的列表9</li>
      <li>分类的列表10</li>
      <li>分类的列表11</li>
      <li>分类的列表12</li>
      <li>分类的列表13</li>
      <li>分类的列表14</li>
      <li>分类的列表15</li>
      <li>分类的列表16</li>
      <li>分类的列表17</li>
      <li>分类的列表18</li>
      <li>分类的列表19</li>
      <li>分类的列表20</li>
      <li>分类的列表21</li>
      <li>分类的列表22</li>
      <li>分类的列表23</li>
      <li>分类的列表24</li>
      <li>分类的列表25</li>
      <li>分类的列表26</li>
      <li>分类的列表27</li>
      <li>分类的列表28</li>
      <li>分类的列表29</li>
      <li>分类的列表30</li>
      <li>分类的列表31</li>
      <li>分类的列表32</li>
      <li>分类的列表33</li>
      <li>分类的列表34</li>
      <li>分类的列表35</li>
      <li>分类的列表36</li>
      <li>分类的列表37</li>
      <li>分类的列表38</li>
      <li>分类的列表39</li>
      <li>分类的列表40</li>
      <li>分类的列表41</li>
      <li>分类的列表42</li>
      <li>分类的列表43</li>
      <li>分类的列表44</li>
      <li>分类的列表45</li>
      <li>分类的列表46</li>
      <li>分类的列表47</li>
      <li>分类的列表48</li>
      <li>分类的列表49</li>
      <li>分类的列表50</li>
      <li>分类的列表51</li>
      <li>分类的列表52</li>
      <li>分类的列表53</li>
      <li>分类的列表54</li>
      <li>分类的列表55</li>
      <li>分类的列表56</li>
      <li>分类的列表57</li>
      <li>分类的列表58</li>
      <li>分类的列表59</li>
      <li>分类的列表60</li>
      <li>分类的列表61</li>
      <li>分类的列表62</li>
      <li>分类的列表63</li>
      <li>分类的列表64</li>
      <li>分类的列表65</li>
      <li>分类的列表66</li>
      <li>分类的列表67</li>
      <li>分类的列表68</li>
      <li>分类的列表69</li>
      <li>分类的列表70</li>
      <li>分类的列表71</li>
      <li>分类的列表72</li>
      <li>分类的列表73</li>
      <li>分类的列表74</li>
      <li>分类的列表75</li>
      <li>分类的列表76</li>
      <li>分类的列表77</li>
      <li>分类的列表78</li>
      <li>分类的列表79</li>
      <li>分类的列表80</li>
      <li>分类的列表81</li>
      <li>分类的列表82</li>
      <li>分类的列表83</li>
      <li>分类的列表84</li>
      <li>分类的列表85</li>
      <li>分类的列表86</li>
      <li>分类的列表87</li>
      <li>分类的列表88</li>
      <li>分类的列表89</li>
      <li>分类的列表90</li>
      <li>分类的列表91</li>
      <li>分类的列表92</li>
      <li>分类的列表93</li>
      <li>分类的列表94</li>
      <li>分类的列表95</li>
      <li>分类的列表96</li>
      <li>分类的列表97</li>
      <li>分类的列表98</li>
      <li>分类的列表99</li>
      <li>分类的列表100</li>
    </ul>
  </div>
</template>

<script>
  import BScroll from 'better-scroll'

  export default {
    name: "category",
    data() {
      return {
        scroll: null
      }
    },

    mounted() {
      this.scroll = new BScroll(document.querySelector('.wrapper'), {
        // 监听滚动
        probeType: 3,
        // 监听上拉加载更多
        pullUpLoad: true
      })

      this.scroll.on('scroll', (position) => {
        // console.log(position);
      })

      this.scroll.on('pullingUp', () => {
        console.log('上拉加载更多');
      })
    }
  }
</script>

<style scoped>
  .wrapper {
    height: 150px;
    background-color: red;

    overflow: hidden;
    /*overflow-y: scroll;*/
  }
</style>
