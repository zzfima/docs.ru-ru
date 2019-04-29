---
title: Рекомендации по настройке конструктора рабочих процессов
ms.date: 03/30/2017
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
ms.openlocfilehash: 2d6ef24d00baa4df6dfc8e0af69c1d489b79a41f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945994"
---
# <a name="customizing-the-workflow-design-experience"></a>Рекомендации по настройке конструктора рабочих процессов

Сценарии для разработки пользовательских действий и повторного размещения [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] были значительно упрощены в [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]. Разработка и развертывание упрощены и являются более гибкими по сравнению с предыдущими версиями. Основное изменение инфраструктуры состоит является то, что новый модель программирования конструктора действий построена на Windows Presentation Foundation (WPF). Это позволяет декларативно определять конструкторы действий и упрощает повторное размещение [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] в других приложениях. При повторном размещении может быть создан редактор пользовательских выражений, поддерживающий IntelliSense, или упрощенный домен выражений. Интеграция с Windows Communication Foundation (WCF) также стала более плавной с использованием служб рабочих процессов. Конструкторы пользовательских действий и дерево элементов модели могут быть использованы для улучшения действий во время разработки во вновь размещенных конструкторах рабочих процессов.

## <a name="in-this-section"></a>В этом разделе

 [Настраиваемые конструкторы и шаблоны действий](using-custom-activity-designers-and-templates.md)

 Описывается порядок создания новых конструкторов и шаблонов пользовательских действий.

 [Отдельное размещение конструктора рабочих процессов](rehosting-the-workflow-designer.md)

 Описывается способ повторного размещения [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] вне Visual Studio и способ отображения ошибок проверки.

 [Настраиваемый редактор выражений](using-a-custom-expression-editor.md)

 В этой статье описывается реализация редактора пользовательских выражений для использования с конструкторами рабочих процессов, повторно размещенными вне Visual Studio 2010.

## <a name="reference"></a>Ссылка

<xref:System.Activities.Presentation.ActivityDesigner>

## <a name="see-also"></a>См. также

- [Расширение Windows Workflow Foundation](extend.md)
- [Конструктор](./samples/designer.md)
- [Пользовательские конструкторы действий](./samples/custom-activity-designers.md)
- [Повторное размещение конструктора](./samples/designer-rehosting.md)