<template>
    <div class="row row-cards">
        <div class="col-xl-3 col-lg-4">
            <div class="row">
                <div class="col-md-12 col-lg-12">
                    <div class="card">
                        <div class="card-header">
                            <div class="card-title">Kategori</div>
                        </div>
                        <div class="card-body">
                            <ul class="list-group">
                                <li class="list-group-item border-0 p-0"> <a href="javascript:void(0)"><i class="fe fe-chevron-right"></i> Mens </a><span class="product-label">22</span> </li>
                                <li class="list-group-item border-0 p-0"> <a href="javascript:void(0)"><i class="fe fe-chevron-right"></i> Womens </a><span class="product-label">15</span> </li>
                                <li class="list-group-item border-0 p-0"> <a href="javascript:void(0)"><i class="fe fe-chevron-right"></i> Kids </a><span class="product-label">10</span> </li>
                                <li class="list-group-item border-0 p-0"> <a href="javascript:void(0)"><i class="fe fe-chevron-right"></i> Others </a><span class="product-label">88</span> </li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="col-xl-9 col-lg-8">
            <div class="row">
                <div class="col-xl-12">
                    <div class="card p-0">
                        <div class="card-body p-4">
                            <div class="row">
                                <div class="col-xl-5 col-lg-8 col-md-8 col-sm-8">
                                    <div class="input-group d-flex w-100 float-start">
                                        <input type="text" class="form-control border-end-0 my-2" placeholder="Search ...">
                                        <button class="btn input-group-text bg-transparent border-start-0 text-muted my-2">
                                            <i class="fe fe-search text-muted" aria-hidden="true"></i>
                                        </button>
                                    </div>
                                </div>
                                <div class="col-xl-4 col-lg-4 col-md-4 col-sm-4">
                                    <ul class="nav item2-gl-menu float-end my-2">
                                        <li class="border-end"><a href="#tab-11" class="show active" data-bs-toggle="tab" title="List style"><i class="fa fa-th"></i></a></li>
                                        <li><a href="#tab-12" data-bs-toggle="tab" class="" title="Grid"><i class="fa fa-list"></i></a></li>
                                    </ul>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="tab-content">
                <div class="tab-pane active" id="tab-11">
                    <div class="row">
                        <div v-for="item in list" v-bind:key="item.id" class="col-md-6 col-xl-4 col-sm-6">
                            <div class="card">
                                <div class="product-grid6">
                                    <div class="product-image6 p-5">
                                        <ul class="icons">
                                            <li><a href="#" class="btn btn-primary"> <i class="fe fe-eye">  </i> </a></li>
                                            <li><a href="#" class="btn btn-success"><i class="fe fe-edit"></i></a></li>
                                            <li><a href="#" class="btn btn-danger"><i class="fe fe-x"></i></a></li>
                                        </ul>
                                        <a href="#" >
                                            <img class="img-fluid br-7 w-100" src="assets/images/pngs/9.jpg" alt="img">
                                        </a>
                                    </div>
                                    <div class="card-body pt-0">
                                        <div class="product-content text-center">
                                            <h1 class="title fw-bold fs-20"><a href=#>{{ item.nama_menu }}</a></h1>
                                            <div class="mb-2 text-warning">
                                                <i class="fa fa-star text-warning"></i>
                                                <i class="fa fa-star text-warning"></i>
                                                <i class="fa fa-star text-warning"></i>
                                                <i class="fa fa-star-half-o text-warning"></i>
                                                <i class="fa fa-star-o text-warning"></i>
                                            </div>
                                            <div class="price">{{item.harga}}</div>
                                        </div>
                                    </div>
                                    <div class="card-footer text-center">
                                        <a href="#" class="btn btn-primary mb-1"><i class="fe fe-shopping-cart mx-2"></i>Add to cart</a>
                                        <a href="#" class="btn btn-outline-primary mb-1"><i class="fe fe-heart mx-2 wishlist-icon"></i>Add to wishlist</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>


    <div class="row">
        <div class="col-lg-12 col-md-12 col-sm-12 col-xl-12">
            <div class="card overflow-hidden">
                <div class="card-header">
                    Data Kategori
                </div>
                <div class="card-body">
                    <div class="table-responsive">
                        <table class="table table-bordered text-nowrap text-md-nowrap mg-b-0"                       >
                            <thead>
                                <tr>
                                    <th>ID</th>
                                    <th>Nama Menu</th>
                                    <th>Harga</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr v-for="item in list" v-bind:key="item.id">
                                    <td>{{item.id}}</td>
                                    <td>{{item.nama_menu}}</td>
                                    <td>{{item.harga}}</td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios';
export default {
    data()
    {
        return {list:undefined}
    },
    mounted()
    {
        axios.get('http://spicesignature.com/api/menu')
        .then((response)=>{
            this.list=response.data.data;
            // console.warn(resp.data.data)
        })
    }
}
</script>
