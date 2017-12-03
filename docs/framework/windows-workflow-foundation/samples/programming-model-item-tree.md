---
title: "Программирование дерева элементов модели"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0229efde-19ac-4bdc-a187-c6227a7bd1a5
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fc58f5d91618c8b4caa97da12b7b0e20e007448c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="programming-model-item-tree"></a>Программирование дерева элементов модели
В этом образце показано, как переходить по дереву <xref:System.Activities.Presentation.Model.ModelItem>, используя привязку декларативных данных из представления дерева [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)].  
  
## <a name="sample-details"></a>Подробные сведения об образце  
 Дерево <xref:System.Activities.Presentation.Model.ModelItem> является абстракцией, которая используется инфраструктурой [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] для предоставления данных о базовом изменяемом экземпляре. На следующей иллюстрации показаны различные слои инфраструктуры внутри [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].  
  
 ![Архитектура конструктора рабочих процессов](../../../../docs/framework/windows-workflow-foundation/samples/media/workflowdesignerarch.JPG "WorkflowDesignerArch")  
  
 Элемент <xref:System.Activities.Presentation.Model.ModelItem> состоит из указателя базового значения, а также коллекции объектов <xref:System.Activities.Presentation.Model.ModelProperty>. Объект <xref:System.Activities.Presentation.Model.ModelProperty> в свою очередь включает данные, такие как имя и тип свойства, и указатель значения, который в свою очередь является еще одним элементом <xref:System.Activities.Presentation.Model.ModelItem>. Преобразователь значений используется для манипуляции некоторыми элементами <xref:System.Activities.Presentation.Model.ModelItem>, возвращаемыми свойством <xref:System.Activities.Presentation.Model.ModelProperty>, чтобы они правильно отображались в представлении дерева. Далее в образце показано, как императивно программировать с использованием дерева <xref:System.Activities.Presentation.Model.ModelItem> при помощи императивных инструкций, в соответствии со следующим примером.  
  
```csharp  
ModelItem mi = wd.Context.Services.GetService<ModelService>().Root;  
ModelProperty mp = mi.Properties["Activities"];  
mp.Collection.Add(new Persist());  
ModelItem justAdded = mp.Collection.Last();  
justAdded.Properties["DisplayName"].SetValue("new name");  
```  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Откройте решение ProgrammingModelItemTree.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Постройте решение, выбрав **построить решение** из **построения** меню.  
  
3.  Нажмите клавишу F5 для запуска приложения. Будет показана форма [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)].  
  
4.  Нажмите кнопку **загрузить WF** кнопку, чтобы загрузить <xref:System.Activities.Presentation.Model.ModelItem> и привязать его к представлению дерева.  
  
5.  Щелкнув **изменить дерево элементов модели** кнопку выполняется предшествующий код, чтобы добавить элемент в дерево и задает свойство.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ProgrammingModelItemTree`  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Data.IValueConverter>
