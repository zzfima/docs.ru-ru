---
title: "Рекомендации по настройке конструктора рабочих процессов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9916e30812e167e108a1ca9b958aa6d15fbd1f41
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="customizing-the-workflow-design-experience"></a>Рекомендации по настройке конструктора рабочих процессов
Сценарии для разработки пользовательских действий и повторного размещения [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] были значительно упрощены в [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]. Разработка и развертывание упрощены и являются более гибкими по сравнению с предыдущими версиями. Основное изменение инфраструктуры состоит в том, что новая модель программирования конструктора действий построена на основе [!INCLUDE[avalon1](../../../includes/avalon1-md.md)]. Это позволяет декларативно определять конструкторы действий и упрощает повторное размещение [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] в других приложениях. При повторном размещении может быть создан редактор пользовательских выражений, поддерживающий IntelliSense, или упрощенный домен выражений. Интеграция с [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] стала более плавной с использованием служб рабочих процессов. Конструкторы пользовательских действий и дерево элементов модели могут быть использованы для улучшения действий во время разработки во вновь размещенных конструкторах рабочих процессов.  
  
## <a name="in-this-section"></a>Содержание  
 [Настраиваемые конструкторы и шаблоны действий](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md)  
 Описывается порядок создания новых конструкторов и шаблонов пользовательских действий.  
  
 [Отдельное размещение конструктора рабочих процессов](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 Описывается способ повторного размещения [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] вне [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] и отображения ошибок проверки.  
  
 [Настраиваемый редактор выражений](../../../docs/framework/windows-workflow-foundation/using-a-custom-expression-editor.md)  
 Описан способ реализации редактора пользовательских выражений для использования с конструкторами рабочих процессов, повторно размещенными вне [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Activities.Presentation.ActivityDesigner>  
  
## <a name="see-also"></a>См. также  
 [Расширение Windows Workflow Foundation](../../../docs/framework/windows-workflow-foundation/extend.md)  
 [Конструктор](../../../docs/framework/windows-workflow-foundation/samples/designer.md)  
 [Пользовательские конструкторы действий](../../../docs/framework/windows-workflow-foundation/samples/custom-activity-designers.md)  
 [Повторное размещение конструктора](../../../docs/framework/windows-workflow-foundation/samples/designer-rehosting.md)
