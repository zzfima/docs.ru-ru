---
title: "Задание 1. Создание нового приложения Windows Presentation Foundation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Задание 1. Создание нового приложения Windows Presentation Foundation
В данной задаче необходимо создать пустое приложение [!INCLUDE[avalon1](../../../includes/avalon1-md.md)], используя шаблон WPF Application Visual Studio, и добавить ссылки на соответствующие сборки рабочего процесса [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)].  
  
### Создание проекта приложения WPF  
  
1.  Откройте [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)], в меню **Файл** укажите **Новый**, затем выберите **Проект**.  
  
2.  В диалоговом окне **Новый проект** выберите **Visual C\#** или **Visual Basic** в области **Установленные шаблоны** в левой части окна.Если выбранный язык не отображается, разверните узел **Другие языки**.  
  
3.  В области **Установленные шаблоны** выберите **Windows**.  
  
4.  Убедитесь в том, что в раскрывающемся списке в верхней области выбрано **.NET Framework 4** \(значение по умолчанию\), затем выберите **Приложение WPF**.  
  
5.  В качестве имени проекта укажите **HostingApplication** в нижней части экрана.  
  
6.  В качестве имени решения укажите **RehostingTheDesigner**.  
  
7.  Нажмите кнопку **ОК**, чтобы создать проект приложения.[!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] создает основной пользовательский интерфейс WPF для приложения и включает в него соответствующий XAML и файлы с фоновым кодом.  
  
8.  Добавьте ссылки на сборки **WorkflowModel**.Для этого в **Обозревателе решений** щелкните правой кнопкой мыши проект **HostingApplication** и выберите **Добавление ссылки**.  
  
9. В диалоговом окне **Добавление ссылки** перейдите на вкладку **.NET**, удерживая нажатой клавишу CTRL, выберите следующие сборки, а затем нажмите **ОК**:  
  
    -   System.Activities  
  
    -   System.Activities.Presentation  
  
    -   System.Activities.Core.Presentation  
  
10. Нажмите кнопку **ОК**.  
  
11. Дополнительные сведения о том, как разместить средство визуальной разработки конструктора рабочих процессов, см. в разделе [Задание 2. Размещение конструктора рабочих процессов](../../../docs/framework/windows-workflow-foundation//task-2-host-the-workflow-designer.md).  
  
## См. также  
 [Повторное размещение конструктора рабочих процессов](../../../docs/framework/windows-workflow-foundation//rehosting-the-workflow-designer.md)   
 [Задание 2. Размещение конструктора рабочих процессов](../../../docs/framework/windows-workflow-foundation//task-2-host-the-workflow-designer.md)