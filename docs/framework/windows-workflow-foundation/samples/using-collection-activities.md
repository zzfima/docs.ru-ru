---
title: "Использование действий с коллекциями"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e1977cf8-1695-4071-b946-7046fe39601e
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: aa7b3b6815adfba9367585174b242aa7410d578e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="using-collection-activities"></a>Использование действий с коллекциями
В этом образце демонстрируется использование действий коллекции (<xref:System.Activities.Statements.AddToCollection%601>, <xref:System.Activities.Statements.ClearCollection%601>, <xref:System.Activities.Statements.ExistsInCollection%601> и <xref:System.Activities.Statements.RemoveFromCollection%601>) с классом, реализующим интерфейс <xref:System.Collections.ICollection>, и создание пользовательского действия, которое выполняет итерацию по коллекции для распечатки содержания каждого из элементов коллекции. Пользовательское действие, называемое `PrintCollection`, выводит на консоль элементы коллекции с названием `Numbers`.  
  
 В следующей таблице представлены четыре действия, посредством которых осуществляется управление коллекциями в рабочих процессах.  
  
|Название действия|Описание|  
|-------------------|-----------------|  
|<xref:System.Activities.Statements.AddToCollection%601>|Добавляет элемент в коллекцию.|  
|<xref:System.Activities.Statements.ClearCollection%601>|Очищает коллекцию, удаляя все элементы.|  
|<xref:System.Activities.Statements.ExistsInCollection%601>|Если элемент присутствует в коллекции, возвращает `true`.|  
|<xref:System.Activities.Statements.RemoveFromCollection%601>|Удаляет элемент из коллекции.|  
  
 Образец состоит из двух решений, одно из которых находится в каталоге CodedWorkflow, а другое - в каталоге DesignerWorkflow. Они демонстрируют два разных способа использования действий для выполнения одинаковых задач.  
  
|Решение|Описание|Основные файлы|  
|-|-|-|  
|CodedWorkflow|Образец клиентского приложения, демонстрирующий, как вызывать действия коллекции программным образом.|**PrintCollection.cs**: вспомогательное действие для вывода каждого элемента в коллекции на консоль.<br /><br /> **Program.cs**: программным образом создает последовательное действие, содержащее ряд действий коллекции и выполняет его.|  
|DesignerWorkflow|Образец клиентского приложения, демонстрирующий, как декларативно использовать действия коллекции в конструкторе рабочего процесса.|**CollectionWorkflow.xaml**: рабочий процесс, созданный декларативно с конструктором, использующим действия коллекции.<br /><br /> **PrintCollection.cs**: вспомогательное действие для вывода каждого элемента в коллекции на консоль.<br /><br /> **Program.cs**: вызывает рабочий процесс, описанный в CollectionWorkflow.xaml.|  
  
 При демонстрации элементы коллекции `Numbers` выводятся на консоль с использованием определенного пользователем действия под названием `PrintCollection`.  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Используя [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], откройте файл решения Collection.sln.  
  
2.  Для построения решения нажмите CTRL+SHIFT+B.  
  
3.  Чтобы запустить решение, нажмите клавиши CTRL+F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Collection`  
  
## <a name="see-also"></a>См. также
