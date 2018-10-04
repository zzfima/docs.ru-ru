---
title: Параллельное действие ForEach с ограничением
ms.date: 03/30/2017
ms.assetid: f2855b5f-e9a7-433d-96a4-40fc31025215
ms.openlocfilehash: 8691edb8a5a61204b187be8def553f2f06be0f0d
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48581866"
---
# <a name="throttled-parallel-foreach"></a>Параллельное действие ForEach с ограничением
`ThrottleParallelForEach` Аналогично действию <!--zz <xref:System.Activities.Statements.ParallelForEach>--> `System.Activities.Statements.ParallelForEach` действия, за одним исключением, позволяет настроить фактор одновременности для ограничения число одновременно выполняющихся ветвей. Действие `ThrottleParallelForEach` является производным от действия <xref:System.Activities.NativeActivity>, поскольку оно должно планировать другие действия (дочерние действия), что можно сделать только через класс <xref:System.Activities.NativeActivityContext>.

## <a name="projects"></a>Проекты

|**ProjectName**|**Описание**|**Основные файлы**|
|-|-|-|
|ThrottledParallelForEach|Содержит действие `ThrottledParallelForEach` и его конструктор.|ThrottledParallelForEach.cs<br /><br /> Определение действия `ThrottledParallelForEach`.|
|CodeTestClient|Образец клиентского приложения, осуществляющего конфигурирование и запуск рабочего процесса с использованием `ThrottledParallelForEach` при помощи императивного кода.|Program.cs<br /><br /> Определяет и выполняет экземпляр образца рабочего процесса.|

#### <a name="to-use-this-sample"></a>Использование этого образца

1.  С помощью Visual Studio 2010, откройте файл решения ThrottledParallelForEach.sln.

2.  Для построения решения нажмите CTRL+SHIFT+B.

3.  Чтобы запустить решение, нажмите клавишу F5.

> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\ThrottledParallelForEach`