---
title: InvokeMethod
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 04988eb3-65f8-456d-b1bd-509f5d05a57c
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0a480fac4b9dc9313834b78f4bc688c445d7adc6
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2017
---
# <a name="invokemethod"></a>InvokeMethod
В этом образце демонстрируются разные способы использования действия <xref:System.Activities.Statements.InvokeMethod> для вызова методов класса.  
  
 Метод относится к классу и представляет содержащийся набор операций. Действие <xref:System.Activities.Statements.InvokeMethod> предоставляет возможность вызова методов относительно объектов или типов, передачи параметров и получения возвращаемого значения. Методы могут быть вызваны синхронно и асинхронно.  
  
## <a name="sample-details"></a>Подробные сведения об образце  
 В этом образце используется действие <xref:System.Activities.Statements.InvokeMethod> для выполнения следующих сценариев.  
  
1.  Вызовите метод экземпляра без параметров.  
  
2.  Вызовите метод экземпляра с двумя параметрами (<xref:System.String> и <xref:System.Int32>).  
  
3.  Вызовите метод экземпляр с двумя параметрами (<xref:System.String> и <xref:System.Int32>) и массивом параметров типа <xref:System.String>[].  
  
4.  Вызовите метод экземпляра с двумя параметрами типа <xref:System.Int32> и результатом типа <xref:System.Int32>. В этом сценарии значение результата привязано к переменной и используется в другом действии. Значение отображается в консоли при помощи действия <xref:System.Activities.Statements.WriteLine>.  
  
5.  Вызовите статический метод экземпляра с двумя параметрами типа <xref:System.String> и <xref:System.Int32>.  
  
6.  Вызовите метод экземпляра с одним общим параметром типа <xref:System.String>.  
  
7.  Вызовите статический метод с двумя общими параметрами типа <xref:System.String> и <xref:System.Int32>.  
  
8.  Вызовите метод экземпляра, который имеет один параметр типа <xref:System.String>, переданный по ссылке. В этом сценарии параметр ссылки привязан к переменной (`outParam`) и используется в другом действии. Параметр отображается в консоли при помощи действия <xref:System.Activities.Statements.WriteLine>.  
  
9. Вызовите асинхронный метод экземпляра.  
  
10. Вызовите два других действия относительно одного и того же объекта при помощи двух действий <xref:System.Activities.Statements.InvokeMethod>.  
  
11. Сохраните значение в экземпляре объекта.  
  
12. Извлеките значение из экземпляра объекта.  
  
## <a name="to-use-this-sample"></a>Использование этого образца  
 Данный образец предоставляется в двух версиях. В первой версии образца показано использование метода <xref:System.Activities.Statements.InvokeMethod> посредством кода C# с применением модели программирования [!INCLUDE[wf](../../../../includes/wf-md.md)]; версия находится над папкой CodedWorkflow\CS. Во второй версии показано использование метода <xref:System.Activities.Statements.InvokeMethod> при помощи XAML; версия находится под папкой DesignerWorkflow\CS.  
  
#### <a name="to-run-the-coded-workflow-sample"></a>Выполнение образца кода рабочего процесса  
  
1.  Откройте файл решения InvokeMethodUsage.sln из папки CodedWorkflow\CS в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Для построения решения нажмите CTRL+SHIFT+B.  
  
3.  Чтобы запустить решение, нажмите клавиши CTRL+F5.  
  
#### <a name="to-run-the-designer-workflow-sample"></a>Выполнение образца рабочего процесса конструктора  
  
1.  Откройте файл решения InvokeMethodUsage.sln из папки DesignerWorkflow\CS в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Для построения решения нажмите CTRL+SHIFT+B.  
  
3.  Чтобы запустить решение, нажмите клавиши CTRL+F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InvokeMethod`