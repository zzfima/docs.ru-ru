---
title: Действие RangeEnumeration
ms.date: 03/30/2017
ms.assetid: ca5b78f4-94fa-4aa7-830d-26039ac422c8
ms.openlocfilehash: c9cf522227620422b414adc26cbc0bf338bf57d4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43556296"
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
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\RangeEnumeration`