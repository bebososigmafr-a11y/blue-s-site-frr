<template>
    <router-link v-bind:to="'/blackjack/table/' + (table.table + 1)" class="blackjack-tables-element">
        <div class="element-inner">
            <div class="inner-info">
                <div class="info-name">LOBBY {{table.table + 1}}</div>
                <IconUsers />
                <span class="gradient-blue">{{table.players.length}} / 5</span>
            </div>
        </div>
    </router-link>
</template>

<script>
    import IconUsers from '@/components/icons/IconUsers';

    export default {
        name: 'BlackjackTablesElement',
        props: ['table'],
        components: {
            IconUsers
        }
    }
</script>

<style scoped>
    a.blackjack-tables-element {
        width: calc(20% - 8px);
        height: 150px;
        position: relative;
        margin-top: 10px;
        margin-right: 10px;
    }

    a.blackjack-tables-element:nth-child(1),
    a.blackjack-tables-element:nth-child(2),
    a.blackjack-tables-element:nth-child(3),
    a.blackjack-tables-element:nth-child(4),
    a.blackjack-tables-element:nth-child(5) {
        margin-top: 0;
    }

    a.blackjack-tables-element:nth-child(5n) {
        margin-right: 0;
    }

   a.blackjack-tables-element::before {
    content: '';
    width: 100%;
    height: 100%;
    position: absolute;
    top: 0;
    left: 0;
    background: linear-gradient(135deg, #1e3a5c 0%, #2d4a76 25%, #3a5b8c 50%, #4a7dff 75%, #6ba1ff 100%);
    box-shadow: inset 0px 0px 25px rgba(0, 0, 0, 0.37), 0 8px 25px rgba(74, 125, 255, 0.3);
    clip-path: polygon(25px 0, calc(100% - 25px) 0, 100% 25%, 100% 75%, calc(100% - 25px) 100%, 25px 100%, 0 75%, 0 25%);
    transition: all 0.3s ease;
}

    a.blackjack-tables-element:hover::before {
    background: linear-gradient(135deg, #2d4a76 0%, #3a5b8c 25%, #4a7dff 50%, #6ba1ff 75%, #8bc1ff 100%);
    box-shadow: inset 0px 0px 25px rgba(0, 0, 0, 0.37), 0 12px 35px rgba(74, 125, 255, 0.5);
    transform: translateY(-2px);
}

    a.blackjack-tables-element::after {
        content: '';
        width: calc(100% - 2px);
        height: calc(100% - 2px);
        position: absolute;
        top: 1px;
        left: 1px;
        background-image: url('~@/assets/img/blackjack/preview.webp');
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover;
        background-color: #031d32;
        clip-path: polygon(25px 0, calc(100% - 25px) 0, 100% 25%, 100% 75%, calc(100% - 25px) 100%, 25px 100%, 0 75%, 0 25%);
    }

    a.blackjack-tables-element .element-inner {
        width: calc(100% - 2px);
        height: calc(100% - 2px);
        position: absolute;
        top: 1px;
        left: 1px;
        background: none;
        clip-path: polygon(25px 0, calc(100% - 25px) 0, 100% 25%, 100% 75%, calc(100% - 25px) 100%, 25px 100%, 0 75%, 0 25%);
        transition: all 0.3s ease;
        z-index: 1;
    }

    a.blackjack-tables-element:hover .element-inner {
    background: radial-gradient(140% 80% at 85% 50%, rgba(74, 125, 255, 0.3) 0%, rgba(0, 0, 0, 0) 100%), linear-gradient(255deg, rgba(107, 161, 255, 0.15) -50%, rgba(74, 125, 255, 0.1) 100%);
}

    a.blackjack-tables-element .inner-info {
        position: absolute;
        display: flex;
        flex-direction: column;
        align-items: center;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
    }

    a.blackjack-tables-element .info-name {
    white-space: nowrap;
    font-family: 'Rubik', sans-serif;
    font-size: 28px;
    font-weight: 900;
    background: linear-gradient(180deg, #ffffff 0%, #cce0ff 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    text-fill-color: transparent;
    text-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
}

    a.blackjack-tables-element .inner-info svg {
        width: 22px;
        height: 19px;
        margin-top: 10px;
    }

    a.blackjack-tables-element .inner-info span {
        margin-top: 1px;
        font-size: 18px;
        font-weight: 800;
    }

    @media only screen and (max-width: 1050px) {

        a.blackjack-tables-element {
            width: calc(25% - 7.5px);
        }

        a.blackjack-tables-element:nth-child(5) {
            margin-top: 10px;
        }

        a.blackjack-tables-element:nth-child(5n) {
            margin-right: 10px;
        }

        a.blackjack-tables-element:nth-child(4n) {
            margin-right: 0;
        }

    }

    @media only screen and (max-width: 900px) {

        a.blackjack-tables-element {
            width: calc(33.33% - 6.66px);
        }

        a.blackjack-tables-element:nth-child(4) {
            margin-top: 10px;
        }

        a.blackjack-tables-element:nth-child(4n) {
            margin-right: 10px;
        }

        a.blackjack-tables-element:nth-child(3n) {
            margin-right: 0;
        }

    }

    @media only screen and (max-width: 700px) {

        a.blackjack-tables-element {
            width: calc(50% - 5px);
        }

        a.blackjack-tables-element:nth-child(3) {
            margin-top: 10px;
        }

        a.blackjack-tables-element:nth-child(3n) {
            margin-right: 10px;
        }

        a.blackjack-tables-element:nth-child(2n) {
            margin-right: 0;
        }

    }
</style>
