<template>
	<div class="outer-container">
		<button class="not-print" @click="print">인쇄하기(1.3)</button>
		<div class="inner-container">
			<div class="dummy-content"></div>
		</div>
	</div>
</template>

<script>
export default {
  setup(){
    const print = () => window.print();
    return {
      print
    }
  }
};
</script>

<style scoped>
	.outer-container {
		display: flex;
		flex-direction: column;
		margin : 0 auto;
		align-items: center;
		font-size: 14px;
		max-width : 1184px;
		padding-bottom: 40px;
	}
	.inner-container {
		width : 100%;
		border-radius: 4px;
		border : 10px solid #cccccc;
		box-shadow: 0 0 8px 0 rgba(0, 0, 0, 0.04);
		background-color: white;
		padding: 0 36px 57px 36px;
	}
  .dummy-content {
    width : 800px;
    height : 1800px;
  }
	@media print {
		.outer-container {
			print-color-adjust: exact !important;
			width: 100%;
			zoom : 90%;
			padding: 0;
		}
    .not-print {
				display: none;
			}
	}
	@page {
		size: A4;
    margin : 1.3in;
    margin-bottom: 0;
	}
</style>
