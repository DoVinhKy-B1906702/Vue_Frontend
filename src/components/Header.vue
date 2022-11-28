<template>
    <header class="header">
        <div class="logo">
            <div class="logo-text">{{header}}</div>
        </div>
        <div>
            <ul class="headerList">
                <li class="headerList-item">
                    <a class="headerList-text" href="">Trang chủ</a>
                </li>
                <li class="headerList-item">
                    <a class="headerList-text" href="">Trang nhất</a>
                </li>
                <li class="headerList-item">
                    <a class="headerList-text" href="">Trang nhì</a>
                </li>
                <li  class="headerList-item">
                    <a class="headerList-text" href="">Trang ba</a>
                </li>
            </ul>
        </div>
        <div>
            <div>Đăng xuất</div>
        </div>
    </header>
</template>
<script>
export default {
    name: 'HeaderItem',
    props: {header: String}
}

</script>

<style scoped>
.header {
    display: flex;
    text-align: center;
    align-items: center;
    justify-content:space-between;
    background: #333;
    color: #fff;
    padding: 0 24px;
}
.logo {
    cursor: pointer;
}
.logo-text {
    font-size: 2rem;
    padding: 8px;
    margin: 8px;
}
.headerList {
    display: flex;
    flex: 1;
    padding-left: 0;
}
.headerList-item {
    list-style: none;
    padding: 8px;
    margin: 8px;
    border-bottom: 1px solid #fff;
}
.headerList-text {
    text-decoration: none;
    color: #fff;
}
</style>