---
title: "Проверка связей действий | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6f11a34e-ed67-4bce-88ce-7e96bbb4d052
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Проверка связей действий
Этот образец состоит из трех действий: `CreateCity`, `CreateState`и `CreateCountry`.Действие `CreateCity` должно быть внутри действия `CreateState`, а `CreateState` должно быть внутри действия `CreateCountry`.Для этого образца логика проверки реализуется в коде для действия `CreateState` и в XAML для действия `CreateCity`.Оба ограничения имеют одинаковое поведение.  
  
 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] предоставляет следующие три вспомогательных действия, которые позволяют разработчику проверять связи между действиями.  
  
 <xref:System.Activities.Validation.GetParentChain>  
 Предоставляет коллекцию из всех действий, принадлежащих родительскому узлу текущего узла.  
  
 <xref:System.Activities.Validation.GetChildSubtree>  
 Предоставляет коллекцию из всех действий, принадлежащих поддереву текущего узла, за исключением самого текущего узла.  
  
 <xref:System.Activities.Validation.GetWorkflowTree>  
 Предоставляет коллекцию из всех действий в том же дереве, что и текущий узел.  
  
 В образце действие <xref:System.Activities.Statements.ForEach%601> используется для прохождения коллекции, возвращаемой действием <xref:System.Activities.Validation.GetParentChain>.Тип каждого элемента в коллекции сравнивается с типом результата действия `CreateCountry` \(или действия `CreateState`, если проверяется `CreateCity`\), и после нахождения соответствия флаг результата устанавливается в `true`.Наконец <xref:System.Activities.Validation.AssertValidation> используется для формирования ошибки проверки, если флаг результата установлен в `false`.  
  
### Использование этого образца  
  
1.  Откройте образец решения ContainmentValidation.sln в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Постройте решение.  
  
3.  Чтобы запустить программу, нажмите сочетание клавиш CTRL\+F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец находится в следующем каталоге:  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Basic\Validation\ActivityRelationships`  
  
## См. также