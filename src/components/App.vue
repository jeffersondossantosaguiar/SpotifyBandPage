<template>
	<Page
		actionBarHidden="true"
		backgroundSpanUnderStatusBar="true"
		@loaded="onPageLoaded"
        backgroundColor="black"
		color="white"
	>
		<GridLayout rows="80, 300, *">
			<Image
				id="img"
				row="1"
				src="~/assets/images/carreta.jpeg"
				android:margin="-100 0 0 0"
			/>
			<ScrollView row="2" android:marginTop="-375" @scroll="onScroll">
				<GridLayout rows="380, *">
					<Label row="0" class="fade" android:marginTop="-50" />
					<Label
						row="0"
						id="title"
						:text="title"
						textWrap="true"
						class="title"
						android:marginTop="150"
					/>
					<Label
						row="0"
						id="title"
						text="8.471.521 OUVINTES MENSAIS"
						textWrap="true"
						class="subtitle"
						android:marginTop="300"
					/>
					<Label
						row="1"
						:text="content"
						textWrap="true"
						android:margin="20 20 20 30"
					/>
				</GridLayout>
			</ScrollView>
			<Label row="0" id="blackBar" class="black-bar" android:marginTop="580" />
			<Button
				row="0"
				id="btnPlay"
				text="ORDEM ALEATÓRIA"
				class="btn-play"
				android:marginTop="660"
				@tap="onButtonTap"
			/>
			<Label
				row="0"
				id="abTitle"
				:text="title"
				class="ab-title"
				android:marginTop="20"
			/>
		</GridLayout>
	</Page>
</template>

<script >
import { ScrollEventData, ScrollView } from "tns-core-modules/ui/scroll-view";
import { Image } from "tns-core-modules/ui/image";

export default {
	data() {
		return {
            abTitle: {},
			title: `Hurricane Truck`,
			content: `Siga em frente, olhe para o lado
Se liga no mestiço na batida do cavaco
Siga em frente, olhe para o lado
Se liga no mestiço na batida do cavaco
Quero ver o som de Bob Marley sacudindo o partideiro
O reggae da jamaica no embolada
Eu vou mostrar pro mundo inteiro
Mundo inteiro
Siga em frente, olhe para o lado
Se liga no mestiço na batida do cavaco
Siga em frente, olhe para o lado
Se liga no mestiço na batida do cavaco
Vamos passo a passo outra vez 1, 2, 3
Vou pôr no remelexo vocês 1, 2, 3
É fácil de aprender, é só se resolver
Se liga no mestiço que agora ele chegou de vez
Por que não pode?
Se o corpo quer remexer
Até o Freud
Vai fazer você entender
Como é que pode?
Se você dança, seu esqueleto, ele balança

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed sed dui nec lorem luctus porta. Morbi ultricies interdum molestie. Donec nec lacus vitae dolor iaculis ultricies quis in diam. Etiam sit amet tristique eros, eget tempus sem. Donec mauris lectus, fringilla vel eleifend nec, hendrerit eget nisl. Praesent fermentum posuere aliquet. Phasellus vitae est in risus ullamcorper commodo. Nullam nisi urna, luctus eu urna ut, viverra vestibulum justo.

Integer ultrices aliquet nisi vel commodo. Sed tempor felis risus, vehicula iaculis risus sollicitudin ut. Mauris tincidunt, orci sodales feugiat porttitor, dui mi fringilla dui, ac posuere elit urna semper lorem. Nunc est elit, pulvinar vitae felis ut, rhoncus rutrum ex. Morbi tempor sit amet dui in interdum. Aliquam erat volutpat. Pellentesque rutrum malesuada leo, vitae tempor nibh imperdiet vitae. Integer rhoncus facilisis bibendum. In hac habitasse platea dictumst. Donec massa diam, pulvinar auctor ipsum eget, finibus volutpat dolor. Sed arcu leo, cursus in lobortis a, molestie vel nunc. Fusce vitae nisl sed leo aliquet efficitur quis quis arcu. Aenean posuere tempus porta. Sed posuere auctor ullamcorper. Quisque nec commodo mi, et mollis dolor.

Quisque ut faucibus mi, et finibus ante. Proin malesuada ante et mauris scelerisque iaculis. Curabitur sodales auctor dolor, vel fringilla sapien congue eu. Curabitur dictum diam eu sollicitudin eleifend. Vivamus consequat elit eu rhoncus malesuada. Sed cursus placerat urna eu convallis. Etiam sit amet placerat est, et viverra velit. Donec in tellus suscipit, egestas lacus vitae, ullamcorper ligula. Aliquam quam erat, semper non lorem non, vulputate placerat libero. Nunc aliquam urna tortor, id commodo felis aliquam eu. Nulla lobortis tincidunt odio, non sagittis diam pharetra id. Nulla auctor diam at mi blandit, vitae lacinia tortor accumsan. Vestibulum fringilla tempor augue non varius. Fusce vitae pharetra velit, vel maximus massa.

Proin lacinia, magna eget pretium suscipit, lectus ligula placerat neque, eget elementum diam odio quis leo. Quisque id arcu aliquam, placerat dui dictum, finibus felis. Phasellus ultricies justo in purus aliquam tristique. Vestibulum urna dolor, egestas sit amet feugiat quis, rutrum nec sapien. Aliquam ut leo efficitur, blandit elit sed, consequat libero. Proin sed blandit arcu. Quisque pulvinar, nulla finibus sagittis lacinia, libero mi accumsan mauris, in feugiat dui odio non sapien. Curabitur dictum ultricies leo et bibendum. Integer a porta erat, at accumsan magna. Pellentesque magna lacus, dignissim sit amet turpis condimentum, tristique imperdiet lorem. Donec efficitur ornare mi nec iaculis. Nam faucibus maximus justo, ut tincidunt mauris congue ut. Sed varius malesuada lorem, ac sodales elit euismod in. Praesent tristique sollicitudin odio vitae dictum. Fusce non dolor ut purus suscipit semper.

Aenean vulputate odio ut maximus aliquet. Nulla ultrices turpis vel nulla cursus, sit amet tincidunt sapien viverra. Praesent facilisis dapibus mattis. Maecenas malesuada sagittis nisl vitae lacinia. Donec vulputate at mauris at ornare. Mauris elementum sapien sit amet lacinia lacinia. Interdum et malesuada fames ac ante ipsum primis in faucibus. Etiam tellus leo, blandit non leo ac, sagittis consectetur erat. Nullam gravida, nulla vitae laoreet sodales, eros ipsum pellentesque lectus, nec rhoncus justo erat ut mi. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus..
        `,
		};
	},
	methods: {
		onButtonTap() {
			console.log("Button");
		},
		onPageLoaded(args) {
			const page = args.object;
			const blackBar = page.getViewById("blackBar");
            blackBar.opacity = 0;
            
			this.abTitle = page.getViewById("abTitle");
			this.abTitle.opacity = 0;
		},
		onScroll(args) {
			const scrollView = args.object;
			const page = scrollView.page;

			const image = page.getViewById("img");
			const btnPlay = page.getViewById("btnPlay");
			const blackBar = page.getViewById("blackBar");

			/* console.log(`scrollY: ${args.scrollY}`); */

			if (args.scrollY < 0) {
				const scrollAmt = Math.abs(args.scrollY);
				const scale = (scrollAmt + 300) / 300;
				image.scaleX = scale;
				image.scaleY = scale;
				image.translateY = scrollAmt / 2;

				btnPlay.translateY = scrollAmt;
				blackBar.translateY = scrollAmt;
			} else {
				image.translateY = -1 * args.scrollY;

				if (args.scrollY < 300) {
					btnPlay.translateY = args.scrollY * -1;
					blackBar.translateY = args.scrollY * -1;

					if (args.scrollY > 100) {

                        const abTitleOpacity = this.scaleFormula(args.scrollY, 280, 300, 0, 1)
                        this.abTitle.opacity = abTitleOpacity

						const opacity = this.scaleFormula(
							args.scrollY,
							200,
							380,
							0,
							1
						);
						blackBar.opacity = opacity;
					}
				} else {
					btnPlay.translateY = -300;
					blackBar.translateY = -300;
                    blackBar.opacity = 1;
                    this.abTitle.opacity = 1;
				}
			}
		},
		scaleFormula(current, totalMin, totalMax, scaledMin, scaledMax) {
			return (
				((scaledMax - scaledMin) * (current - totalMin)) /
					(totalMax - totalMin) +
				scaledMin
			);
		},
	},
};
</script>

<style scoped>
.ab-title {
	font-size: 20;
	font-weight: 800;
	color: white;
	text-align: center;
}
.title {
	font-size: 60;
	font-weight: 800;
	color: white;
	text-align: center;
}
.subtitle {
	font-size: 10;
	color: white;
	text-align: center;
}
.fade {
	background: linear-gradient(to top, black, transparent);
	width: 100%;
	height: 380;
}
.black-bar {
	background-color: black;
	width: 100%;
	height: 110;
}
.btn-play {
	width: 200;
	height: 50;
	border-radius: 25;
	background-color: #1aba54;
	color: white;
	font-weight: bold;
}
</style>
