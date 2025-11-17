---
title: Как войти в Консоль Администратора
description: 
published: true
date: 2025-11-17T15:08:57.127Z
tags: 
editor: markdown
dateCreated: 2025-11-17T15:08:57.127Z
---


#### Вход в консоль администратора
<html>
<head>
    <style>
        .video-player-container {
            margin: 20px 0;
        }
        .video-source-selector {
            margin-bottom: 10px;
        }
        .source-btn {
            padding: 8px 16px;
            background: #f0f0f0;
            border: 1px solid #ddd;
            cursor: pointer;
            margin-right: 5px;
            border-radius: 4px;
            font-family: Arial, sans-serif;
            font-size: 14px;
            transition: all 0.3s ease;
        }
        .source-btn:hover {
            background: #e0e0e0;
        }
        .source-btn.active {
            background: #45688e;
            color: white;
            border-color: #45688e;
        }
        .video-frame {
            width: 560px;
            height: 315px;
            max-width: 100%;
        }
        .video-frame iframe {
            width: 100%;
            height: 100%;
            border: none;
        }
    </style>
<meta charset="utf-8">
<meta name="keywords" content="консоль администратора, консоль администрирования, вход в консоль, hubex, хабекс, хубекс, хабикс"/>
</head>
<body>
<p>Ознакомьтесь с обучающим видеороликом <strong>Консоль администратора в HubEx</strong>. В нем мы рассказываем обо всех возможностях консоли. Подробные инструкции для каждого раздела консоли представлены в <a href="https://wiki.hubex.ru/index_admin.html">текущем разделе</a> нашей базы знаний. </p>

<div class="video-player-container" data-player-id="player3">
    <div class="video-source-selector">
        <button class="source-btn active" data-source="vk">VK</button>
        <button class="source-btn" data-source="youtube">YouTube</button>
    </div>
    <div class="video-embed">
        <div class="video-frame youtube-frame" style="display: none;">
            <iframe src="https://www.youtube.com/embed/5qsg9aUpIlw?si=v98J92BDBRDR7-r-" loading="lazy" allow="accelerometer; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
        </div>
        <div class="video-frame vk-frame" style="display: block;">
            <iframe src="https://vkvideo.ru/video_ext.php?oid=-187865475&id=456239129&hd=2&autoplay=0" allowfullscreen></iframe>
        </div>
    </div>
</div>

<p>Войти в консоль администратора можно в web-приложении HubEx: нажмите на значок
    с вашим аватаром в правом верхнем углу, затем выберите пункт <strong>Консоль администратора</strong>.</p>
<div>
    <img style="margin: 0 auto; display: block; max-width: 95%;"
         src="/attachments/images/FAQ/ADMIN/EnterTheAdm/Avatar.jpg"/>
</div>
<p>
<div>
    <img style="margin: 0 auto; display: block; max-width: 95%;"
         src="/attachments/images/FAQ/ADMIN/EnterTheAdm/AdmConsole.jpg"/>
</div>
</p>


<p>В новом окне откроется консоль администратора. На основной странице находится информация о вашем аккаунте:
    подписка, количество пользователей и т.д. Слева располагается меню консоли. С помощью меню в консоли администратора
    можно настраивать <strong>Роли</strong>, <strong>Участки</strong>, <strong>Жизненные циклы</strong> и т.д. </p>

<div>
    <img style="margin: 0 auto; display: block; max-width: 80%;"
         src="/attachments/images/FAQ/ADMIN/EnterTheAdm/AdmConsole2.jpg"/>
</div>

<p>Если вы не смогли войти в консоль, значит у вас не хватает прав доступа. Обратитесь в <strong>Чат с
    поддержкой</strong> в web-приложении или на почту <a href="mailto:support@hubex.ru" target="_blank" rel="noopener">
        support@hubex.ru</a>.</p>
<p>Кнопка для перехода в <strong>Чат с поддержкой</strong> и к обучающим статьям находится рядом с вашим аватаром (красный вопросительный знак).</p>
<div>
    <img style="margin: 0 auto; display: block; max-width: 80%;"
         src="/attachments/images/FAQ/ADMIN/EnterTheAdm/Help.jpg"/>
</div>

<script>
    function hideSiblingVideo(activeVideo){
        const nextSibling=activeVideo.nextElementSibling
        const prevSibling=activeVideo.previousElementSibling
        if(nextSibling){
            nextSibling.style.display="none"
        }
        if(prevSibling){
            prevSibling.style.display="none"
        }
    }
 
    function switchActiveButtons(activeButton){
        const nextSibling=activeButton.nextElementSibling
        const prevSibling=activeButton.previousElementSibling
        const activeClass="active"
        if(nextSibling){
            nextSibling.classList.remove(activeClass)
        }
        if(prevSibling){
            prevSibling.classList.remove(activeClass)
        }
        activeButton.classList.add(activeClass)
        return activeButton?.dataset?.source
    }

    function switchShowVideos(activeContainer,label){
        const videoClass=`video-frame ${label}-frame`
        const videoFrame=activeContainer.querySelector(videoClass)
        const videos=activeContainer.children[1].children
        const activeVideo=Array.from(videos).filter((item)=>item.className===videoClass)
        console.debug({activeVideo})
        hideSiblingVideo(activeVideo[0])
        activeVideo[0].style.display="block"
    }

    const allVideoContainers=document.querySelectorAll(".video-player-container")
    allVideoContainers.forEach((container)=>{
        container.addEventListener("click",(e)=>{
            if(!e.target.classList.contains('source-btn')) return;
            
            console.debug({e},{container})
            const targetButton=e.target
            const activeSource=switchActiveButtons(targetButton)
            console.debug(activeSource)
            if(activeSource){
                switchShowVideos(container,activeSource)
            }
        })
    })
</script>

</body>
</html>

___
### Следующие шаги:
- [Настройка ролей](./Roles.md)
- [Настройка участков](./Places.md)
- [Типы оборудования](./ObjectsType.md)


____
- [Перейти в меню](http://wiki.hubex.ru)