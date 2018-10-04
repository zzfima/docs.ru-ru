---
title: Разработка действий рабочих процессов с помощью класса Activity
ms.date: 03/30/2017
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
ms.openlocfilehash: bfe117de9d284353ce46766c828ce209e5391f38
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48580028"
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a>Разработка действий рабочих процессов с помощью класса Activity
Самый простой способ создать действие с помощью Windows Workflow Foundation (WF) в [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] заключается в создании класса, который наследует от <xref:System.Activities.Activity> создающего функциональность путем сборки пользовательских действий или действий из [встроенные Библиотека действий](../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md). В этом разделе показано, как создать действие для вывода двух сообщений на консоль.

### <a name="to-create-a-custom-activity-using-the-activity-designer"></a>Для создания пользовательского действия с помощью конструктора действий сделайте следующее:

1.  Откройте Visual Studio 2012.

2.  Выберите в меню «Файл» пункт «Создать», затем пункт «Создать проект». Выберите **Workflow 4.0** под **Visual C#** в **типы проектов** затем выберите **v2010** узла. Выберите **библиотеки действий** в **шаблоны** окна. Задайте имя для нового проекта HelloActivity.

3.  Откройте окно создания нового действия.  Перетащите действие <xref:System.Activities.Statements.Sequence> из области элементов в область конструктора.

4.  Перетащите действие <xref:System.Activities.Statements.WriteLine> в действие <xref:System.Activities.Statements.Sequence> activity. Введите `"Hello World"` (с кавычками) в **текст** поля.

5.  Перетащите второе действие <xref:System.Activities.Statements.WriteLine> в действие <xref:System.Activities.Statements.Sequence> под первым. Введите `"Goodbye"` (с кавычками) в **текст** поля.
