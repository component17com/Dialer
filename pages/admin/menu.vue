<template>
  <div class="admin-container">
    <el-tree :data="data" :props="defaultProps" @node-click="handleNodeClick"></el-tree>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        data: [{
          label: 'Level one 1',
          children: [{
            label: 'Level two 1-1',
            children: [{
              label: 'Level three 1-1-1'
            }]
          }]
        }, {
          label: 'Level one 2',
          children: [{
            label: 'Level two 2-1',
            children: [{
              label: 'Level three 2-1-1'
            }]
          }, {
            label: 'Level two 2-2',
            children: [{
              label: 'Level three 2-2-1'
            }]
          }]
        }, {
          label: 'Level one 3',
          children: [{
            label: 'Level two 3-1',
            children: [{
              label: 'Level three 3-1-1'
            }]
          }, {
            label: 'Level two 3-2',
            children: [{
              label: 'Level three 3-2-1'
            }]
          }]
        }],
        defaultProps: {
          children: 'children',
          label: 'label'
        }
      };
    },
    methods: {
      handleNodeClick(data) {
        console.log(data);
      }
    }
  };
</script>

<style lang="scss">
  .expanded{
    .el-icon-caret-right:before{
      content: "\002D";
    }
  }
  .el-icon-caret-right:before{
    content: "\002B";
  }

  @keyframes openLeft {
    from {height: 0}
    to {height: calc(100% - 50px);}
  }
  @keyframes closeLeft {
    from {height: calc(100% - 50px);}
    to {height: 0px;}
  }
  @media screen and (min-width: 768px) and (max-width: 991px){
    .admin-container{
      .admin__left {
        position: absolute;
        top: 50px;
        display: flex;
        flex-direction: column;
        width: 100%;
        height: 0;
        min-width: 0;
        max-width: 100%;
        background-color: #303133;
        overflow: hidden;
        .left__models{
          overflow-x: hidden;
        }
        .admin__left-buttons{
          display: flex;
          align-items: center;
          padding:5px 15px;
        }
      }
      .adminLeftClose{
        animation: closeLeft  0.3s linear;
        animation-fill-mode: forwards;
      }
      .adminLeftOpen{
        animation: openLeft  0.3s linear;
        animation-fill-mode: forwards;
        &::-webkit-scrollbar {
          width: 4px;
        }

        &::-webkit-scrollbar-thumb {
          background: #cccccc;
        }

        &::-webkit-scrollbar-track {
          background: #888888;
          cursor: pointer;
        }
      }
      .adminLeftOver{
        overflow-y: auto;
      }
      .admin__left-button{
        display: block;
        button{
          display: flex;
          align-items: center;
          justify-content: center;
          border: none;
          padding: 0;
          background-color: transparent;
          width: 50px;
          height: 50px;
          font-size: 30px;
          color: white;
        }
      }
      .right__header-top{
        display: none;
      }
      .right__header-buttons {
        padding: 7px 15px 8px 0;
      }
      .left__model {
        white-space: nowrap;
        text-overflow: ellipsis;
        overflow: hidden;
      }
    }
  }
</style>
