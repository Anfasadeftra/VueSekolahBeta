<template>
    <nav class="navbar navbar-expand-md navbar-dark bg-dark">
  <div class="container-fluid">
    <a class="navbar-brand" href="#">SELAMAT DATANG</a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse">
      <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        <li class="nav-item"><router-link to="/">
          <a class="nav-link active" aria-current="page" href="/index">Beranda</a></router-link>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="/jasa">Sewa Jasa</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="/contack">Kontak</a>
        </li>
      </ul>
      <form class="d-flex" role="search">
        <a class="btn btn-primary" href="/jasa" role="button">SEWA JASA</a>
      </form>
    </div>
  </div>
</nav>
</template>