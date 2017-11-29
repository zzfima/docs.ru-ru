---
title: "Действие RangeEnumeration"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ca5b78f4-94fa-4aa7-830d-26039ac422c8
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 024cdc9ae082171fb33a63493ac0fbfdd45d3c72
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="rangeenumeration-activity"></a>Действие RangeEnumeration
В этом образце демонстрируется создание пользовательского действия, выполняющего итерацию по коллекции чисел. В следующей таблице приведены основные файлы, содержащиеся в образце.  
  
|Имя файла|Описание|  
|---------------|-----------------|  
|RangeEnumeration.cs|Определяет пользовательское действие с названием `RangeEnumeration`, которое переопределяет класс <xref:System.Activities.NativeActivity> и перебирает в цикле ряд чисел.|  
|RangeEnumerationSample.cs|Клиентское приложение, использующее действие `RangeEnumeration` для итерации по коллекции чисел.|  
  
 В приведенной ниже таблице показаны свойства действия `RangeEnumeration`.  
  
|Свойство|Описание|  
|--------------|-----------------|  
|Запуск|Целое число, с которого начинается цикл.|  
|Остановить|Целое число, на котором заканчивается цикл.|  
|Шаг|Указывает, в каком объеме проводить итерацию каждый раз.|  
|Body|Указывает код для выполнения в ходе каждой итерации.|  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Используя [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], откройте файл решения RangeEnumeration.sln.  
  
2.  Для построения решения нажмите CTRL+SHIFT+B.  
  
3.  Чтобы запустить решение, нажмите клавиши CTRL+F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\RangeEnumeration`  
  
## <a name="see-also"></a>См. также
