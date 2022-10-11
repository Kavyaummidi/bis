<script setup>
import { storeToRefs } from 'pinia';

import { useAuthStore, useUsersStore } from '@/stores';

const authStore = useAuthStore();
const { user: authUser } = storeToRefs(authStore);

const usersStore = useUsersStore();
const { users } = storeToRefs(usersStore);

usersStore.getAll();
</script>

<script>
export default {
    data () {
      return {
        tableData: [
         {
          date: '07-10-2022',
          fees_date: '10-10-2022',
          fees_paid: 'fees paid',
          response_date: '07-10-2022',
          response_reason: "response",
          delivery_status: "response",
          payment_id: '001',
          notice_id: '002',
          last_updated: '07-10-2022'       
          }
        ],
      }
    },
  }
  </script>

<template>
    <div class="row">
        <nav class="mobile-header">
            <div class="navbar-fixed-top">
                <div class="d-flex justify-content-between">
                    <div class="mobile-logo-sec">
                        <a class="logo-sec">
                            <div class="d-flex align-self-start">
                                <img src="src\assets\images\switch_access_shortcut_add_FILL0_wght400_GRAD0_opsz48.png"
                                    alt="">
                                <img src="src\assets\images\TN Dept of Revenue ColorPMS ┬«.png"
                                    style="width: 14%; padding: 1%;" alt="">
                            </div>
                        </a>
                    </div>
                    <div class="mobile-toggle">
                        <div class="">
                            <img src="src\assets\images\notification_important_FILL0_wght400_GRAD0_opsz48.png" alt="">
                            <img src="src\assets\images\manage_accounts_FILL0_wght400_GRAD0_opsz48.png" alt="">
                        </div>
                    </div>
                </div>
            </div>
        </nav>
        <div class="row">
            <div class="col-sm-2">
                <div class="card">
                    <div class="">
                        <div class="sidebar-submenu">
                            <ul class="ul-padding">
                                <li class="menu"><a class="menu-item">Insurance Notice Maintenance</a></li>
                                <li class="menu"><a class="menu-item"> Insurer Maintenance</a></li>
                                <li class="menu"><a class="menu-item">System Maintenance</a></li>
                                <li class="menu"><a class="menu-item">Reporting Dashboard</a></li>
                                <li class="menu"><a class="menu-item">All EIVS Report</a></li>
                                <li class="menu"><a class="menu-item">Renawal Review Grid</a></li>
                                <hr class="solid">
                                <li class="menu"><a class="menu-item">Unverified Grid </a></li>
                                <li class="menu"><a class="menu-item">Insurer Policy Formats</a></li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>
            <div class="col-sm-9">
                <div class="card" id="id1">
                    <div class="card-body">
                        <div id="medNeon">
                            <div class="page-header">
                                <div class="row mb-3">
                                    <div class="col-md-4">
                                        <div class="detail-item">
                                            <label class="details-label">Search by:</label>
                                            <button class="btn btn-outline-secondary dropdown-toggle" type="button"
                                                data-bs-toggle="dropdown" aria-expanded="false"></button>
                                            <ul class="dropdown-menu dropdown-menu-end">
                                                <li><a class="dropdown-item">Action</a></li>
                                                <li><a class="dropdown-item">Another action</a></li>
                                                <li><a class="dropdown-item">Something else here</a></li>
                                            </ul>
                                        </div>
                                    </div>
                                    <div class="col-md-3">
                                        <div class="input-group">
                                            <input type="search" class="form-control rounded" placeholder="Search"
                                                aria-label="Search" aria-describedby="search-addon" />
                                            <button type="button" class="btn btn-outline-primary">Search</button>
                                        </div>
                                    </div>
                                    <div class="col-md-4 danger">
                                        <span>Review Needed : Exemption</span>
                                    </div>
                                </div>
                                <div class="row">
                                    <div class="col-md-4">
                                        <div class="col-md-4 input-group">
                                            <div>Months unconfirmed : </div>
                                            <div class="mb-2">NN</div>
                                            <div class="input-group">
                                                <div>Registration status : </div>
                                                <div class="mb-2">Active</div>
                                            </div>
                                        </div>
                                    </div>
                                    <div class="col-md-4">
                                        <div class="col-md-4 input-group">
                                            <div>Total due : </div>
                                            <div class="mb-2">123</div>
                                            <div class="input-group">
                                                <div>Pin : </div>
                                                <div class="mb-2">123</div>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                            <hr>
                            <div class="list-content">
                                <div class="container">
                                    <v-simple-table class="table">
                                        <template v-slot:default>
                                            <thead>
                                                <tr>
                                                    <th class="text-left">
                                                        Date
                                                    </th>
                                                    <th class="text-left">
                                                        Fees Due
                                                    </th>
                                                    <th class="text-left">
                                                        Fees Paid
                                                    </th>
                                                    <th class="text-left">
                                                        Response Date
                                                    </th>
                                                    <th class="text-left">
                                                        Response Reason
                                                    </th>
                                                    <th class="text-left">
                                                        Delivery Status
                                                    </th>
                                                    <th class="text-left">
                                                        Payment ID
                                                    </th>
                                                    <th class="text-left">
                                                        Notice ID
                                                    </th>
                                                    <th class="text-left">
                                                        Last Updated
                                                    </th>
                                                </tr>
                                            </thead>
                                            <tbody>
                                                <tr class="itemsList" v-for="item in tableData" :key="item.date">
                                                    <td>{{ item.date }}</td>
                                                    <td>{{ item.fees_date }}</td>
                                                    <td>{{ item.fees_paid }}</td>
                                                    <td>{{ item.response_date }}</td>
                                                    <td>{{ item.response_reason }}</td>
                                                    <td>{{ item.delivery_status }}</td>
                                                    <td>{{ item.payment_id }}</td>
                                                    <td>{{ item.notice_id }}</td>
                                                    <td>{{ item.last_updated }}</td>
                                                </tr>
                                            </tbody>
                                        </template>
                                    </v-simple-table>
                                    <div class="card-footer">
                                        <div class="form-actions">
                                            <div class="primary-actions">
                                                <button class="btn btn-cancel cp" type="button">EIVS Comments
                                                    (N)</button>

                                                <button class="btn btn-cancel cp" type="button">View VTRS
                                                    Record</button>

                                                <button class="btn btn-cancel cp" type="button">Edit Use</button>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="card" id="id2" style="display: none;">
                    <div class="card-body">Menu 2 content</div>
                </div>
                <div class="card" id="id3" style="display: none;">
                    <div class="card-body">Menu 3 content</div>
                </div>
                <div class="card" id="id4" style="display: none;">
                    <div class="card-body">Menu 4 content</div>
                </div>

                <v-row no-gutters>
                    <v-col cols="12" sm="6">
                        <v-card max-width="444" outlined>
                            <v-list-item three-line>
                                <v-list-item-content>
                                    <div class="text-overline mb-6 text-left">
                                        <v-row no-gutters>
                                            <v-col>
                                                <h3>Insurance Coverage</h3>
                                            </v-col>
                                            <v-col>
                                                <div class="text-right">
                                                    <v-btn class="ma-2" :loading="loading" :disabled="loading"
                                                        color="secondary" @click="loader = 'loading'">
                                                        Verify Insurance
                                                    </v-btn>
                                                </div>
                                            </v-col>
                                        </v-row>
                                        <hr>
                                    </div>
                                    <v-list-item-title class="text-h5 mb-1">
                                        <v-row no-gutters>
                                            <v-col cols="12" sm="6">
                                                <h6>Insurance Company</h6>
                                            </v-col>
                                            <v-col cols="12" sm="6">
                                                <v-text-field :rules="rules"></v-text-field>
                                            </v-col>

                                            <v-col cols="12" sm="6">
                                                <h6>NAIC ID</h6>
                                            </v-col>
                                            <v-col cols="12" sm="6">
                                                <v-text-field :rules="rules"></v-text-field>
                                            </v-col>

                                            <v-col cols="12" sm="6">
                                                <h6>Effective Date</h6>
                                            </v-col>
                                            <v-col cols="12" sm="6">
                                                <v-text-field :rules="rules"></v-text-field>
                                            </v-col>

                                            <v-col cols="12" sm="6">
                                                <h6>Policy Number</h6>
                                            </v-col>
                                            <v-col cols="12" sm="6">
                                                <v-text-field :rules="rules"></v-text-field>
                                            </v-col>

                                            <v-col cols="12" sm="6">
                                                <h6>Last Updated</h6>
                                            </v-col>
                                            <v-col cols="12" sm="6">
                                                <v-text-field :rules="rules"></v-text-field>
                                            </v-col>
                                        </v-row>
                                    </v-list-item-title>
                                </v-list-item-content>
                            </v-list-item>
                        </v-card>
                    </v-col>
                    <v-col cols="12" sm="6">
                        <v-card max-width="444" outlined>
                            <v-list-item three-line>
                                <v-list-item-content>
                                    <div class="text-overline mb-6 text-left">
                                        <v-row no-gutters>
                                            <v-col>
                                                <h3>Exemptions <span>**Review Needed**</span></h3>
                                            </v-col>
                                            <v-col>
                                                <div class="text-right">
                                                    <v-btn class="ma-2" :loading="loading" :disabled="loading"
                                                        color="secondary" @click="loader = 'loading'">
                                                        Edit
                                                    </v-btn>
                                                </div>
                                            </v-col>
                                        </v-row>
                                        <hr>
                                    </div>
                                    <v-list-item-title class="text-h5 mb-1">
                                        <v-row no-gutters>
                                            <v-col cols="12" sm="6">
                                                <h6>Exemption Reason</h6>
                                            </v-col>
                                            <v-col cols="12" sm="6">
                                                <v-text-field :rules="rules"></v-text-field>
                                            </v-col>

                                            <v-col cols="12" sm="6">
                                                <h6>Exempt Active Date</h6>
                                            </v-col>
                                            <v-col cols="12" sm="6">
                                                <v-text-field :rules="rules"></v-text-field>
                                            </v-col>

                                            <v-col cols="12" sm="6">
                                                <h6>Exempt Expiration Date</h6>
                                            </v-col>
                                            <v-col cols="12" sm="6">
                                                <v-text-field :rules="rules"></v-text-field>
                                            </v-col>

                                            <v-col cols="12" sm="6">
                                                <h6>Last Updated</h6>
                                            </v-col>
                                            <v-col cols="12" sm="6">
                                                <v-layout row wrap id="lastUpdated">
                                                    <v-text-field dense outline single-line></v-text-field>
                                                </v-layout>
                                            </v-col>
                                        </v-row>
                                    </v-list-item-title>
                                </v-list-item-content>
                            </v-list-item>
                        </v-card>
                    </v-col>
                </v-row>
            </div>

        </div>
    </div>
</template>
  
<style scoped>
  .sidebar-wrapper
  {
      width: 280px!important;
  }
  
  hr {
    margin: 1rem 0;
    color: inherit;
    border: 0;
    border-top: 0px solid;
    opacity: .25;
  }
  
  .ul-padding{
    padding: 10px !important;
  }
  .btn-set{
    cursor: pointer;
    color: #fff!important;
    background-color: #42a7d7 !important;
    border-color: #42a7d7 !important;
  }
  .danger{
    text-align: end;
    color: red;
  }
  hr.solid {
    border-top: 3px solid #bbb;
  }
  
  .row-align{
    width: 21% !important;
  }
  /*--------------------------page-content-----------------------------*/
  .page-wrapper .page-content {
    display: inline-block;
    width: 100%;
    padding-left: 0px;
    padding-top: 0px;
  }
  
  .page-wrapper .page-content > #content {
    min-height: 100vh;
    padding-left: 65px;
    padding-top: 10px;
  }
  
  .page-wrapper.toggled .page-header {
    padding-left: 0px;
  }
  
  .page-wrapper .page-content {
    overflow-x: hidden;
  }
  
  .sidebar-wrapper.toggled {
    z-index: 0px;
    width: 0px;
  }
  
  /*----------------------sidebar-menu-------------------------*/
  .sidebar-wrapper .sidebar-menu .header-menu span {
    font-weight: bold;
    font-size: 14px;
    padding: 15px 20px 5px 20px;
    display: inline-block;
    border-color: #e3ebf6;
  }
  
  .sidebar-wrapper .sidebar-menu ul li a {
    display: inline-block;
    width: 100%;
    text-decoration: none;
    position: relative;
    padding: 8px 0px 8px 0;
  }
  
  .sidebar-wrapper .sidebar-menu .sidebar-dropdown.active > a {
    background: #2e8ebc;
    border-radius: 4px;
    padding: 4px 3px;
  }
  
  .sidebar-wrapper .sidebar-menu .sidebar-dropdown.active > a {
    color: #ffffff !important;
  }
  
  .sidebar-wrapper .sidebar-menu ul li a i {
    font-size: 14px;
    width: 30px;
    height: 30px;
    line-height: 30px;
    text-align: center;
    border-radius: 4px;
    background: #fcfcfc;
    margin-right: 4px;
  }
  
  .sidebar-wrapper .sidebar-menu ul li a:hover > i::before {
    display: inline-block;
  }
  
  .sidebar-wrapper .sidebar-menu .sidebar-dropdown > a:after {
    font-family: "Font Awesome 5 Free";
    font-weight: 900;
    content: "\f105";
    font-style: normal;
    display: inline-block;
    font-style: normal;
    font-variant: normal;
    text-rendering: auto;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    background: 0 0;
    position: absolute;
    right: 15px;
    top: 12px;
  }
  
  .menu:hover{
      background: #D9EAFA;
      color: #0073DC;
      border: 1px solid #D9EAFA;
      font-weight: 400;
      border-radius: 6px;
      margin-right: 15px;
  }
  .sidebar-wrapper .sidebar-menu .sidebar-dropdown .sidebar-submenu ul {
    padding: 5px 0;
  }
  
  .sidebar-wrapper .sidebar-menu .sidebar-dropdown .sidebar-submenu li {
    padding-left: 20px;
    font-size: 13px;
  }
  
  
  .sidebar-org-name{
    text-align: center;
    max-width: 122px;
    margin: 0 auto;
    
  }
  h6{
      font-weight: 600 !important;
      color: #2E8EBC !important;
      font-size: 15px !important;
    }
  .p-sidebar-org-name {
      margin: 0px;
      padding-left: 10px;
    }
  
  /*----------------sidebar-content----------------*/
  .sidebar-content {
    max-height: calc(100% - 0px);
    height: calc(100% - 0px);
    overflow-y: auto;
    padding-left: 20px;
    padding-right: 15px;
    background-color: #fff;
    border-right: 1px solid #e5e5e5;
    position: relative;
  }
  
  .sidebar-content.toggled {
    left: -300px;
  }
  
  .sidebar-content.toggled #show-sidebar {
    margin-left: 65px;
  }
  
  .sidebar-content.toggled .page-header {
    padding-left: 100px;
  }
  
  .sidebar-content.desktop {
    overflow-y: hidden;
  }
  
  /*--------------------sidebar-brand----------------------*/
  .sidebar-wrapper .sidebar-brand {
    padding: 10px 0px 10px 10px;
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-align: center;
        -ms-flex-align: center;
            align-items: center;
  }
  
  .sidebar-wrapper .sidebar-brand .logo {
    width: 120px;
    height: 30px;
    -o-object-fit: contain;
       object-fit: contain;
  }
  
  .sidebar-wrapper .sidebar-brand > a {
    text-transform: uppercase;
    font-weight: bold;
    -webkit-box-flex: 1;
        -ms-flex-positive: 1;
            flex-grow: 1;
  }
  
  .sidebar-wrapper .sidebar-brand #close-sidebar {
    cursor: pointer;
    font-size: 20px;
  }
  
  
  /*----------------sidebar-wrapper----------------*/
  .sidebar-wrapper {
    width: 280px;
    height: 100%;
    max-height: 100%;
    position: fixed;
    top: 0;
    z-index: 0;
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
  }
  
  .sidebar-wrapper .sidebar-mini {
    background-color: #2e8ebc;
    max-width: 60px;
    min-width: 60px;
    position: fixed;
    height: 100%;
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-orient: vertical;
    -webkit-box-direction: normal;
        -ms-flex-direction: column;
            flex-direction: column;
    -ms-flex-wrap: nowrap;
        flex-wrap: nowrap;
    -webkit-box-pack: justify;
        -ms-flex-pack: justify;
            justify-content: space-between;
    -webkit-box-align: center;
        -ms-flex-align: center;
            align-items: center;
    z-index: 2;
  }
  
  .sidebar-wrapper .sidebar-mini .sb-mini-brand {
    text-align: center;
  }
  
  .sidebar-wrapper .sidebar-mini .sb-mini-brand img {
    height: 45px;
    width: 45px;
    padding: 6px;
    -o-object-fit: contain;
    object-fit: contain;
    margin: 3px auto;
  }
  
  .sidebar-wrapper .sidebar-mini .mini-sidebar-menu .module-menus {
    margin-top: 20px;
  }
  
  .sidebar-wrapper .sidebar-mini .mini-sidebar-menu .module-menus .menu-item {
    margin-bottom: 15px;
  }
  
  .sidebar-wrapper .sidebar-mini .mini-sidebar-menu .module-menus .menu-item:hover a {
    background: white !important;
    background: #2e8ebc !important;
    -webkit-box-shadow: 0 2px 5px 0 rgba(0, 0, 0, 0.16), 0 2px 10px 0 rgba(0, 0, 0, 0.12);
            box-shadow: 0 2px 5px 0 rgba(0, 0, 0, 0.16), 0 2px 10px 0 rgba(0, 0, 0, 0.12);
    border: 1.2px solid #fff;
  }
  
  .sidebar-wrapper .sidebar-mini .mini-sidebar-menu .module-menus .menu-item a {
    width: 40px;
    height: 40px;
    margin-left: 3px;
    font-size: 19px;
    color: #ffffff;
    border-radius: 40px;
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-align: center;
        -ms-flex-align: center;
            align-items: center;
    -webkit-box-pack: center;
        -ms-flex-pack: center;
            justify-content: center;
  }
  
  .sidebar-wrapper .sidebar-mini .mini-sidebar-menu .module-menus .menu-item-active a {
    background-color: #005c97 !important;
  }
  
  .sidebar-wrapper .sidebar-mini .mini-sidebar-menu .module-menus .menu-item + .active a {
    color: #ffffff;
    background: white;
    background: #207ca9;
    -webkit-box-shadow: 0 2px 5px 0 rgba(0, 0, 0, 0.16), 0 2px 10px 0 rgba(0, 0, 0, 0.12);
            box-shadow: 0 2px 5px 0 rgba(0, 0, 0, 0.16), 0 2px 10px 0 rgba(0, 0, 0, 0.12);
    border: 1.2px solid #fff;
  }
  
  .sidebar-wrapper .sidebar-mini .mini-sidebar-menu .sidebar-menu ul li a {
    display: inline-block;
    width: 100%;
    text-decoration: none;
    position: relative;
    padding: 8px 16px 8px 16px;
  }
  
  .sidebar-wrapper .sidebar-mini .logged-user-actions {
    margin-bottom: 10px;
  }
  
  .sidebar-wrapper .sidebar-mini .logged-user-actions .user-dropdown .user-img {
    width: 40px;
    height: 40px;
    border-radius: 40px;
  }
  
  .sidebar-wrapper .sidebar-mini .logged-user-actions .user-dropdown .logged-user-info {
    padding: 12px 10px;
    text-align: center;
    font-size: 14px;
    border-bottom: 1px solid #ebebeb;
    margin-bottom: 14px;
    padding-bottom: 12px;
  }
  
  .sidebar-wrapper .sidebar-mini .logged-user-actions .user-dropdown .dd-icon {
    margin-right: 10px;
  }
  
  .sidebar-wrapper .sidebar-mini .logged-user-actions .user-dropdown .dropdown-menu {
    top: -12px !important;
    margin-top: 7px !important;
    padding: 0;
    margin-left: 5px;
  }
  
  .sidebar-wrapper .sidebar-mini .logged-user-actions .user-dropdown .dropdown-toggle::after {
    display: none;
  }
  
  .sidebar-wrapper .sidebar-mini .logged-user-actions .user-dropdown .dropdown-item {
    font-size: 13px;
    font-weight: 300;
    padding: 0.5rem 1rem;
  }
  
  .sidebar-wrapper ul {
    list-style-type: none;
    padding: 0;
    margin: 0;
  }
  
  .sidebar-wrapper a {
    text-decoration: none;
  }
  
  /*----------------page-wrapper----------------*/
  .page-wrapper {
    height: 100vh;
  }
  
  .page-wrapper .theme {
    width: 40px;
    height: 40px;
    display: inline-block;
    border-radius: 4px;
    margin: 2px;
  }
  
  .page-wrapper .theme.mn-theme {
    background: #1e2229;
  }
  
  .page-header {
    border-bottom: 1px solid #ededed;
    background-color: #fff;
    padding: 15px 20px;
    justify-content: space-between;
    align-items: center;
  }
  .page-title {
    font-size: 20px;
    margin-bottom: 0;
    display: flex;
  }
  
  .form-group{
      margin-bottom: 1rem;
  }
  
  .page-actions {
    list-style: none;
    margin-bottom: 0;
  }
  
  .form-label{
      color: #565656;
      font-weight: 400;
      font-size: 14px;
  }
  
  .form-control, .form-select{
      font-size: 14px ;
  }
  
  
  ul {
    list-style-type: none;
  }
  
  .nav-link,
  i {
    transition: all 0.5s ease;
    color: #ffdce5;
  }
  .menu-item{
      display: inline-block;
      width: 100%;
      text-decoration: none;
      position: relative;
      padding: 8px 0px 8px 0;
      cursor: pointer;
  }
  .border{
    border: 2px solid rgb(51, 50, 50);
    border-radius: 25px;
    color: white;
    text-align: center;
    background-color: rgb(0 137 255 / 62%)
  }
  .border:hover {
    background-color: #0089ff;
  }
  .border:active{
    background-color:#0089ff;
  }
  ul.nav-list {
    height: 100%;
    padding: 0px 12px 0 10px;
  }
  
  header {
    line-height: 1.5;
    max-height: 100vh;
  }
  
  .logo {
    display: block;
    margin: 0 auto 2rem;
  }
  
  nav {
    width: 100%;
    font-size: 12px;
    text-align: center;
    margin-top: 2rem;
  }
  
  nav a.router-link-exact-active {
    color: var(--color-text);
  }
  
  nav a.router-link-exact-active:hover {
    background-color: transparent;
  }
  
  nav a {
    display: inline-block;
    padding: 0 1rem;
    border-left: 1px solid var(--color-border);
  }
  
  nav a:first-of-type {
    border: 0;
  }
  
  @media (min-width: 1024px) {
    header {
      display: flex;
      place-items: center;
      padding-right: calc(var(--section-gap) / 2);
    }
  
    .logo {
      margin: 0 2rem 0 0;
    }
  
    header .wrapper {
      display: flex;
      place-items: flex-start;
      flex-wrap: wrap;
    }
  
    nav {
      text-align: left;
      margin-left: -1rem;
      font-size: 1rem;
      margin-top: 1rem;
    }
    .nav-bar-icon{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
   }
  }

  /* new css */

  th, td{
  padding:1em;
  border-right: 0em;
  border-left: 0em;
  text-align: center;
  border-bottom: 1px solid #ccc;
}

.itemsList{
  width: 100%;
}

.table{
    display:inline-block;
    border: 1px solid #ccc;
    border-collapse: separate;
    padding-bottom: 1em;
}
tbody{
  padding: 1em;
  margin: 1em;
}
h6{
  font-size: 0.6em;
  font-weight: normal;
}
#lastUpdated .v-input__slot {
    background: #fff !important;
}

  </style>
