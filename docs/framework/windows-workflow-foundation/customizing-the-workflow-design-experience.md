---
title: Рекомендации по настройке конструктора рабочих процессов
ms.date: 03/30/2017
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
ms.openlocfilehash: 41be55391ae9481f6c2e4feb76443f7fb676b69d
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141924"
---
# <a name="customizing-the-workflow-design-experience"></a>Рекомендации по настройке конструктора рабочих процессов

Сценарии создания пользовательских действий и для повторного размещения [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] значительно упрощены в .NET Framework 4. Разработка и развертывание упрощены и являются более гибкими по сравнению с предыдущими версиями. Основное инфраструктуры изменение заключается в том, что новая модель программирования конструктора действий строится на основе Windows Presentation Foundation (WPF). Это позволяет декларативно определять конструкторы действий и упрощает повторное размещение [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] в других приложениях. При повторном размещении может быть создан редактор пользовательских выражений, поддерживающий IntelliSense, или упрощенный домен выражений. Интеграция с Windows Communication Foundation (WCF) стала более простой в использовании служб рабочих процессов. Конструкторы пользовательских действий и дерево элементов модели могут быть использованы для улучшения действий во время разработки во вновь размещенных конструкторах рабочих процессов.

## <a name="in-this-section"></a>Содержание

 [Настраиваемые конструкторы и шаблоны действий](using-custom-activity-designers-and-templates.md)

 Описывается порядок создания новых конструкторов и шаблонов пользовательских действий.

 [Отдельное размещение конструктора рабочих процессов](rehosting-the-workflow-designer.md)

 В этой статье описывается, как повторно разместить [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] за пределами Visual Studio и как отобразить ошибки проверки.

 [Настраиваемый редактор выражений](using-a-custom-expression-editor.md)

 Описание реализации пользовательского редактора выражений для использования с конструкторами рабочих процессов, которые перемещаются вне Visual Studio 2010.

## <a name="reference"></a>Справочники

<xref:System.Activities.Presentation.ActivityDesigner>

## <a name="see-also"></a>См. также

- [Расширение Windows Workflow Foundation](extend.md)
- [Конструктор](./samples/designer.md)
- [Пользовательские конструкторы действий](./samples/custom-activity-designers.md)
- [Повторное размещение конструктора](./samples/designer-rehosting.md)
