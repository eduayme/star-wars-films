<template>
    <footer class="footer-content">
        <a href="https://github.com/eduayme/star-wars-films" target="_blank" >
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M9 19C4.7 20.4 4.7 16.5 3 16M15 21V17.5C15 16.5 15.1 16.1 14.5 15.5C17.3 15.2 20 14.1 20 9.49995C19.9988 8.30492 19.5325 7.15726 18.7 6.29995C19.0905 5.26192 19.0545 4.11158 18.6 3.09995C18.6 3.09995 17.5 2.79995 15.1 4.39995C13.0672 3.87054 10.9328 3.87054 8.9 4.39995C6.5 2.79995 5.4 3.09995 5.4 3.09995C4.94548 4.11158 4.90953 5.26192 5.3 6.29995C4.46745 7.15726 4.00122 8.30492 4 9.49995C4 14.1 6.7 15.2 9.5 15.5C8.9 16.1 8.9 16.7 9 17.5V21" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
            GitHub
        </a>
    </footer>
</template>

<style scoped>
.footer-content {
    display: flex;
    flex-direction: column;
    align-content: center;
    align-items: center;
    justify-content: center;
    padding: 20px 20px 40px 20px;
    background-color: black;
}

a {
    color: white;
    display: flex;
    align-content: center;
    align-items: center;
    justify-content: center;
    padding: 6px 8px;
    gap: 4px;
    text-decoration: none;
    font-size: 20px;
}

a:hover {
    border-radius: 8px;
    transition: box-shadow .25s;
    box-shadow:
        0 3px 6px rgba(0, 0, 0, 0.04),
        0 8px 16px rgba(0, 0, 0, 0.4),
        0 0 0 1px rgba(255, 255, 255, 0.2);
}
</style>