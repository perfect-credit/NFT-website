<template>
  <header>
    <nav class="navbar">
      <h2>Alpha<span class="main__header">ART</span></h2>
      <ul class="navbar__links">
        <li>Collections</li>
        <li>Feature</li>
        <li>FAQ</li>
        <button class="base__button">Select Wallet</button>
      </ul>
    </nav>
  </header>
</template>

<style>
.navbar {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
  gap: 28rem;
}
.navbar h2 {
  cursor: pointer;
  font-weight: 700;
}
.main__header {
  background: linear-gradient(214.02deg, #b75cff 6.04%, #7759a9  92.95%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  font-weight: 700;
  cursor: pointer;
}
.navbar__links {
  list-style: none;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  padding: 10px;
  gap: 40px;
}
.navbar__links li:hover {
  color: #b75cff;
  cursor: pointer;
  transition: 0.3s ease-in-out;
}
.base__button {
  color: white;
  background: linear-gradient(214.02deg, #b75cff 6.04%, #671ae4 92.95%);
  padding: 10px 20px;
  border: none;
  transition: 0.3s ease-in-out;
  border-radius: 10px;
}
.base__button:hover {
  background: linear-gradient(214.02deg, #b75cff 6.04%, #671ae4 92.95%);
  cursor: pointer;
  box-shadow: #671ae4;
  transition: 0.3s ease-in-out;
  transform: translateY(-3px);
}
.base__button:active {
  background: linear-gradient(214.02deg, #b75cff 6.04%, #671ae4 92.95%);
  cursor: pointer;
  box-shadow: #671ae4;
  transition: 0.3s ease-in-out;
  color: #d4aff2;
  transform: translateY(-2px);
}
</style>