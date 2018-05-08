---
title: Разработка и реализация настраиваемых действий
ms.date: 03/30/2017
ms.assetid: 4e30e63d-6e33-4842-a7a4-ce807cef1fad
ms.openlocfilehash: 2ed80b5cbb27c6647053ee9b8f4cd2bedb0c6cde
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="designing-and-implementing-custom-activities"></a>Разработка и реализация настраиваемых действий
Настраиваемые действия в [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] создаются либо посредством сборки системных действий в составные действия, либо путем создания новых типов, производных от <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> или <xref:System.Activities.NativeActivity>. В этом разделе описываются способы создания пользовательских действий обоими способами.  
  
> [!IMPORTANT]
>  Настраиваемые действия по умолчанию отображаются в конструкторе рабочих процессов в виде простого прямоугольника с именем действия. Для создания настраиваемого визуального представления действия в конструкторе рабочих процессов также необходимо создать пользовательский конструктор. Дополнительные сведения см. в разделе [с помощью пользовательских конструкторов действий и шаблоны](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Параметры разработки действий](../../../docs/framework/windows-workflow-foundation/activity-authoring-options-in-wf.md)  
 Описывает стили разработки, доступные в [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].  
  
 [Использование настраиваемого действия](../../../docs/framework/windows-workflow-foundation/using-a-custom-activity.md)  
 Описывает, как добавить пользовательское действие в проект рабочего процесса.  
  
  [Создание асинхронных действий](../../../docs/framework/windows-workflow-foundation/creating-asynchronous-activities-in-wf.md)  
 Описывает создание асинхронных действий.  
  
 [Настройка проверки действий](../../../docs/framework/windows-workflow-foundation/configuring-activity-validation.md)  
 Описывает, как проверка действия может быть использована для выявления ошибок в конфигурации действия до его выполнения.  
  
 [Создание действия в среде выполнения](../../../docs/framework/windows-workflow-foundation/creating-an-activity-at-runtime-with-dynamicactivity.md)  
 Описывает, как создавать действия во время выполнения с помощью <xref:System.Activities.DynamicActivity>.  
  
 [Свойства выполнения рабочего процесса](../../../docs/framework/windows-workflow-foundation/workflow-execution-properties.md)  
 Описывает, как использовать свойства выполнения рабочего процесса для добавления определенных свойств контекста к среде действия.  
  
 [Использование делегатов действий](../../../docs/framework/windows-workflow-foundation/using-activity-delegates.md)  
 Описывает создание и использование действий, содержащих делегаты действий.  
  
 [Локализация действий](../../../docs/framework/windows-workflow-foundation/activity-localization.md)  
 Описывает использование в действиях локализации строковых ресурсов.  
  
 [Использование расширений действий](../../../docs/framework/windows-workflow-foundation/using-activity-extensions.md)  
 Описывает, как создавать и использовать расширения действий.  
  
 [Использование каналов OData из рабочего процесса](../../../docs/framework/windows-workflow-foundation/consuming-odata-feeds-from-a-workflow.md)  
 Описывает различные методы для вызова службы данных WCF из рабочего процесса.  
  
 [Определение области и видимости действия](../../../docs/framework/windows-workflow-foundation/activity-definition-scoping-and-visibility.md)  
 Описывает параметры и правила для определения области данных и видимости элементов для действий.
