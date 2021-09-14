<template>
	<div>
		<div id="container01" class="container default">
			<div class="wrapper">
				<div class="inner">
					<h2 id="text02">{{ details.title }}</h2>
					<p id="text05">
						<span>
							{{ details.description }}
						</span>
					</p>
					<ul id="icons01" class="icons">
						<li>
							<a class="n03" href="https://instagram.com/"
								><img
									src="https://img.icons8.com/material-outlined/24/000000/instagram-new--v2.png"
								/>
								<span class="label">Instagram</span></a
							>
						</li>
						<li>
							<a class="n05" href="tel:0000000000"
								><img
									src="https://img.icons8.com/ios-glyphs/24/000000/phone.png"
								/>
								<span class="label">Phone</span></a
							>
						</li>
						<li>
							<a
								class="n06"
								href="mailto:%68%65%6c%6c%6f%40%63%61%72%72%64%2e%63%6f"
								><img
									src="https://img.icons8.com/material-rounded/24/000000/mail.png"
								/><span class="label">Email</span></a
							>
						</li>
					</ul>
					<ul id="buttons02" class="buttons">
						<li>
							<a @click="updateTab()" class="button n01 cursor-pointer"
								><span class="label selct-none">{{
									details.buttonLabel
								}}</span></a
							>
						</li>
					</ul>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
import { defineComponent, reactive, ref } from "@nuxtjs/composition-api";

export default defineComponent({
	props: ["details"],
	setup() {
		function updateTab() {
			this.$emit("tabs");
		}

		return {
			updateTab,
		};
	},
});
</script>

<style>
</style>