<script>
  import Product from "./Product.svelte";
  import CartItem from "./CartItem.svelte";
  import FamilyNode from "./FamilyNode.svelte";

  let y;

  $: console.log(y);
  let familyStructure = [
    {
      isParent: true,
      name: "Ahmad",
      children: [
        {
          isParent: true,
          name: "Mahmoud",
          children: [
            {
              isParent: false,
              name: "Ala'a"
            }
          ]
        }
      ]
    },
    {
      name: "Khalaf",
      isParent: false
    }
  ];
  let renderedComponent = CartItem;

  function toggle() {
    if (renderedComponent === CartItem) {
      return (renderedComponent = Product);
    }
    renderedComponent = CartItem;
  }
</script>

<svelte:window bind:scrollY={y} />
<button on:click={toggle}>Toggle</button>

<svelte:component
  this={renderedComponent}
  title={renderedComponent === CartItem ? 'Another product' : 'Test product'}
  id="p1" />

{#each familyStructure as familyMember}
  <FamilyNode member={familyMember} />
{/each}
{#each familyStructure as familyMember}
  <FamilyNode member={familyMember} />
{/each}
{#each familyStructure as familyMember}
  <FamilyNode member={familyMember} />
{/each}
{#each familyStructure as familyMember}
  <FamilyNode member={familyMember} />
{/each}
{#each familyStructure as familyMember}
  <FamilyNode member={familyMember} />
{/each}
{#each familyStructure as familyMember}
  <FamilyNode member={familyMember} />
{/each}
