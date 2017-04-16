---
title: "Программирование Windows Forms в Visual Studio с помощью .NET Framework версий 3.0 и 3.5 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 81858ab7-763c-4eac-83fe-d7205e5c4c98
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Программирование Windows Forms в Visual Studio с помощью .NET Framework версий 3.0 и 3.5
Можно использовать [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] для создания проектов, ориентированных на [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] версии 3.0 и 3.5.В этом разделе описано выполнение этой задачи.  
  
> [!NOTE]
>  При добавлении действий убедитесь, что задана необходимая версия [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].Изменение целевой версии рабочего процесса после добавления действия приведет к ошибке проверки рабочего процесса.  
  
> [!WARNING]
>  Открытие существующих рабочих процессов в [!INCLUDE[vs2010](../../../includes/vs2010-md.md)], включающих действия .Net Framework 3.5, приведет к возникновению ошибки в `this.SetValue()`.Чтобы открыть проекты, созданные с помощью предыдущих версий платформы .Net Framework, сначала необходимо открыть пустой рабочий процесс в конструкторе и добавить действие платформы .Net Framework 3.5.  
  
## Создание проекта платформы .NET Framework 3.0 или 3.5 с помощью Visual Studio 2010  
  
1.  Откройте [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  
  
2.  Выберите **Файл**, **Создать**, **Проект**.  
  
3.  В раскрывающемся списке в верхней части диалогового окна выберите необходимую версию [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].  
  
## Обновление целевой версии платформы .NET Framework  
  
1.  В обозревателе решений щелкните правой кнопкой мыши проект и выберите пункт **Свойства**.  
  
2.  В раскрывающемся списке **Требуемая версия .NET Framework** выберите необходимую версию платформы.