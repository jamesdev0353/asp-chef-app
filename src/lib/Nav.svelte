<script>
  import { Collapse, Icon, Nav, Navbar, NavbarBrand, NavItem, NavLink, NavbarToggler } from 'sveltestrap/src';
  import {Popover} from "dumbo-svelte";

  let isOpen = false;

  function handleUpdate(event) {
      isOpen = event.detail.isOpen;
  }
</script>

<Navbar id="navbar" color="dark d-print-none" style="max-height: 1em;" dark expand="md">
  <NavbarBrand href='/' on:click={() => location.assign('/')}>
    <span class="logo">
      ASP Chef (alpha)
    </span>
  </NavbarBrand>
  <NavbarToggler on:click={() => (isOpen = !isOpen)} />
  <Collapse {isOpen} navbar expand="md" on:update={handleUpdate}>
    <Nav class="ms-auto" navbar>
      <Popover title="About">
        <div slot="value">
          <p>
            ASP Chef is a simple, intuitive web app for analysing answer sets without having to deal with complex tools or programming languages.
          </p>
          <p>
            Proudly brought to you by Mario Alviano, Davide Cirimele and Luis Angel Rodriguez Reiners.
          </p>
          <p>
            More details on the GitHub repository <code>https://github.com/alviano/asp-chef</code> (click to open).
          </p>
        </div>
        <NavItem>
          <NavLink href="https://github.com/alviano/asp-chef" target="_blank"><Icon name="question-circle" /></NavLink>
        </NavItem>
      </Popover>
    </Nav>
  </Collapse>
</Navbar>

<style>
  .logo {
    font-family: 'Rock Salt', cursive;
  }
</style>
