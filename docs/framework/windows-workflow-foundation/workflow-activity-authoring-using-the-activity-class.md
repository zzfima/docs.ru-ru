---
title: Разработка действий рабочих процессов с помощью класса Activity
ms.date: 03/30/2017
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
ms.openlocfilehash: 040fe777e332efdfb296e6fb6565935f466ded71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33516208"
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a>Разработка действий рабочих процессов с помощью класса Activity
Самый простой способ создания действия с помощью Windows Workflow Foundation (WF) в [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] необходимо создать класс, наследующий от <xref:System.Activities.Activity> , создающего функциональность путем сборки пользовательских действий или действий для [встроенные Библиотека действий](../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md). В этом разделе показано, как создать действие для вывода двух сообщений на консоль.  
  
### <a name="to-create-a-custom-activity-using-the-activity-designer"></a>Для создания пользовательского действия с помощью конструктора действий сделайте следующее:  
  
1.  Откройте [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].  
  
2.  Выберите в меню «Файл» пункт «Создать», затем пункт «Создать проект». Выберите **Workflow 4.0** под **Visual C#** в **типы проектов** затем выберите **v2010** узла. Выберите **библиотеки действий** в **шаблоны** окна. Задайте имя для нового проекта HelloActivity.  
  
3.  Откройте окно создания нового действия.  Перетащите действие <xref:System.Activities.Statements.Sequence> из области элементов в область конструктора.  
  
4.  Перетащите действие <xref:System.Activities.Statements.WriteLine> в действие <xref:System.Activities.Statements.Sequence> activity. Введите `"Hello World"` (с кавычками) в **текст** поля.  
  
5.  Перетащите второе действие <xref:System.Activities.Statements.WriteLine> в действие <xref:System.Activities.Statements.Sequence> под первым. Введите `"Goodbye"` (с кавычками) в **текст** поля.
