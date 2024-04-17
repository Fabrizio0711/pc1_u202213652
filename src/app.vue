<script setup>
import FooterSection from "./components/footer-section.component.vue";
import Toolbar from "./components/tool-bar.component.vue";
import ProductCard from "./components/product-card.component.vue";
</script>

<template>

    <Toolbar></Toolbar>

      <div class="card">
        <Accordion :activeIndex="0" expandIcon="pi pi-plus" collapseIcon="pi pi-minus">
          <AccordionTab>
            <template #header>
                    <span class="flex align-items-center gap-2 w-full">
                        <span class="font-bold white-space-nowrap">Description</span>
                        <Badge value="3" class="ml-auto mr-2" />
                    </span>
            </template>
            <p class="m-0">
              In this proyect we will develop a conection with a API to get the products and show them in the page by using axios and  PrimeVue library .
            </p>
          </AccordionTab>
          <AccordionTab>
            <template #header>
                    <span class="flex align-items-center gap-2 w-full">
                        <span class="font-bold white-space-nowrap">Products On Sale</span>
                        <Badge value="4" class="ml-auto mr-2" />
                    </span>
            </template>
            <ProductCard></ProductCard>
          </AccordionTab>

        </Accordion>
      </div>

      <FooterSection></FooterSection>



</template>

<style >
footer{
  display:flex;
  justify-content:center;
  align-items:end;

}
</style>
