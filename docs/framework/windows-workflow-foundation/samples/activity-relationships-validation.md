---
title: "Проверка связей действий"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6f11a34e-ed67-4bce-88ce-7e96bbb4d052
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 03ac8e41f8126c6b05eac82d143291a0de491969
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="activity-relationships-validation"></a>Проверка связей действий
Этот образец состоит из трех действий: `CreateCity`, `CreateState` и `CreateCountry`. Действие `CreateCity` должно быть внутри действия `CreateState`, а `CreateState` должно быть внутри действия `CreateCountry`. Для этого образца логика проверки реализуется в коде для действия `CreateState` и в XAML для действия `CreateCity`. Оба ограничения имеют одинаковое поведение.  
  
 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] предоставляет следующие три вспомогательных действия, которые позволяют разработчику проверять связи между действиями.  
  
 <xref:System.Activities.Validation.GetParentChain>  
 Предоставляет коллекцию из всех действий, принадлежащих родительскому узлу текущего узла.  
  
 <xref:System.Activities.Validation.GetChildSubtree>  
 Предоставляет коллекцию из всех действий, принадлежащих поддереву текущего узла, за исключением самого текущего узла.  
  
 <xref:System.Activities.Validation.GetWorkflowTree>  
 Предоставляет коллекцию из всех действий в том же дереве, что и текущий узел.  
  
 В образце действие <xref:System.Activities.Statements.ForEach%601> используется для прохождения коллекции, возвращаемой действием <xref:System.Activities.Validation.GetParentChain>. Тип каждого элемента в коллекции сравнивается с типом результата действия `CreateCountry` (или действия `CreateState`, если проверяется `CreateCity`), а после нахождения соответствия флаг результата устанавливается в `true`. Наконец <xref:System.Activities.Validation.AssertValidation> используется для формирования ошибки проверки, если флаг результата установлен в `false`.  
  
### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Откройте образец решения ContainmentValidation.sln в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Постройте решение.  
  
3.  Чтобы запустить программу, нажмите сочетание клавиш CTRL+F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец находится в следующем каталоге:  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\ActivityRelationships`  
  
## <a name="see-also"></a>См. также
