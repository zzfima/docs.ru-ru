---
title: "Разработка действий рабочих процессов с помощью класса Activity | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Разработка действий рабочих процессов с помощью класса Activity
Самый простой способ создания действия, использующего [!INCLUDE[wf](../../../includes/wf-md.md)] в [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] — это создание класса, наследующего от класса <xref:System.Activities.Activity> и создающего функциональность путем сборки пользовательских действий или действий из [Встроенная библиотека действий](../../../docs/framework/windows-workflow-foundation//net-framework-4-5-built-in-activity-library.md).В этом разделе показано, как создать действие для вывода двух сообщений на консоль.  
  
### Для создания пользовательского действия с помощью конструктора действий сделайте следующее:  
  
1.  Откройте [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].  
  
2.  Выберите в меню «Файл» пункт «Создать», затем пункт «Создать проект».Выберите **Workflow 4.0** в списке **Visual C\#** в разделе **Типы проектов**, затем выберите узел **v2010**.В окне **Шаблоны** выберите **Библиотека действий**.Задайте имя для нового проекта HelloActivity.  
  
3.  Откройте окно создания нового действия.Перетащите действие <xref:System.Activities.Statements.Sequence> из области элементов в область конструктора.  
  
4.  Перетащите действие <xref:System.Activities.Statements.WriteLine> в действие <xref:System.Activities.Statements.Sequence> activity.Введите `"Здравствуй, мир!"` \(с кавычками\) в поле **Текст**.  
  
5.  Перетащите второе действие <xref:System.Activities.Statements.WriteLine> в действие <xref:System.Activities.Statements.Sequence> под первым.Введите `"До свидания!"` \(с кавычками\) в поле **Текст**.