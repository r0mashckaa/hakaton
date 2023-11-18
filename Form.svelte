<script>
	import { createEventDispatcher } from "svelte";
    const dispatch = createEventDispatcher();


    let inpname = '';
	let inpage = '';
	let inpheight = '';
	let inpcity = '';
	let inpfeat = '';

    function onClick(){
        if(inpname.length && inpage.length && inpheight.length && inpcity.length && inpfeat){
            dispatch('add', {text: inpname});
            inpname='';
			dispatch('add', {text: inpage});
            inpage='';
			dispatch('add', {text: inpheight});
            inpheight='';
			dispatch('add', {text: inpcity});
            inpcity='';
			dispatch('add', {text: inpfeat});
            inpfeat='';
        }
    }
</script>

<div class="immg">
	<div class="als">
		<h2 class="title">Форма заявки</h2>
		<div class="forCenter">
			<div>
				<input class="photo" type="file" />
			</div>
			<div class="FVR">
				<div>
					<input bind:value={inpname} type="text" placeholder="ФИО" style="width: 100%;" />
				</div>
				<div>
					<input bind:value={inpage} type="text" placeholder="Возраст" style="width: 100%;" />
				</div>
				<div>
					<input bind:value={inpheight} type="text" placeholder="Рост" style="width: 100%;" />
				</div>
				<div>
					<input bind:value={inpcity} type="text" placeholder="Город" style="width: 100%;" />
				</div>
			</div>
		</div>
		<div class="bottom">
			<div class="features">
				<textarea bind:value={inpfeat} placeholder="Общие черты" rows="5" cols="80" id="TITLE" />
			</div>

			<button class="f" on:click = {onClick}>Отправить</button>
		</div>
	</div>
</div>

<style>
	.immg {
		background: url('/img/bcgrnd.png');
		background-repeat: no-repeat;
		background-size: cover;
		margin: none;
		padding: 15px;
	}
	.photo {
		margin-left: 100px;
	}
	.f {
		border-radius: 0 0 10px 10px;
		margin: 10px;
		width: 609px;
		margin-bottom: 40px;
	}
	.title {
		text-align: center;
		padding: 40px 0;
		background: url('/img/todoimg.png');
		border-bottom: 3px solid black;
		margin-block: 0;
	}
	.FVR {
		display: flex;
		flex-direction: column;
		gap: 40px;
		width: 60%;
	}
	.features {
		display: flex;
		padding-top: 60px;
		justify-content: center;
		width: 100%;
		margin: 10px;
	}
	.bottom {
		display: flex;
		flex-direction: column;
		gap: 30px;
		align-items: center;
	}
	.als {
		width: 50%;
		max-width: 1200px;
		margin: 60px auto;
		border: 4px solid black;
		border-radius: 20px;
		overflow: hidden;
		background: url('/img/todoimg.png');
	}
	.forCenter {
		padding-top: 25px;
		display: flex;
		justify-content: space-between;
		margin: 10px;
		margin-right: 55px;
	}
</style>
