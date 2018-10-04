---
title: Рекомендации по настройке конструктора рабочих процессов
ms.date: 03/30/2017
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
ms.openlocfilehash: ed4ccb45e4470eb03cec856e865d4b50220816e3
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48777543"
---
# <a name="customizing-the-workflow-design-experience"></a>Рекомендации по настройке конструктора рабочих процессов

Сценарии для разработки пользовательских действий и повторного размещения [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] были значительно упрощены в [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]. Разработка и развертывание упрощены и являются более гибкими по сравнению с предыдущими версиями. Основное изменение инфраструктуры состоит является то, что новый модель программирования конструктора действий построена на Windows Presentation Foundation (WPF). Это позволяет декларативно определять конструкторы действий и упрощает повторное размещение [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] в других приложениях. При повторном размещении может быть создан редактор пользовательских выражений, поддерживающий IntelliSense, или упрощенный домен выражений. Интеграция с Windows Communication Foundation (WCF) также стала более плавной с использованием служб рабочих процессов. Конструкторы пользовательских действий и дерево элементов модели могут быть использованы для улучшения действий во время разработки во вновь размещенных конструкторах рабочих процессов.

## <a name="in-this-section"></a>В этом разделе

 [Настраиваемые конструкторы и шаблоны действий](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md)

 Описывается порядок создания новых конструкторов и шаблонов пользовательских действий.

 [Отдельное размещение конструктора рабочих процессов](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)

 Описывается способ повторного размещения [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] вне Visual Studio и способ отображения ошибок проверки.

 [Настраиваемый редактор выражений](../../../docs/framework/windows-workflow-foundation/using-a-custom-expression-editor.md)

 В этой статье описывается реализация редактора пользовательских выражений для использования с конструкторами рабочих процессов, повторно размещенными вне Visual Studio 2010.

## <a name="reference"></a>Ссылка

<xref:System.Activities.Presentation.ActivityDesigner>

## <a name="see-also"></a>См. также

- [Расширение Windows Workflow Foundation](../../../docs/framework/windows-workflow-foundation/extend.md)
- [Конструктор](../../../docs/framework/windows-workflow-foundation/samples/designer.md)
- [Пользовательские конструкторы действий](../../../docs/framework/windows-workflow-foundation/samples/custom-activity-designers.md)
- [Повторное размещение конструктора](../../../docs/framework/windows-workflow-foundation/samples/designer-rehosting.md)