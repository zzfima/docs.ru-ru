---
title: "Использование действия из .NET Framework 3.0 или .NET Framework 3.5 в рабочем процессе .NET Framework 4.5 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6c53fd4c-5dd0-4fb4-ab6b-111302629548
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Использование действия из .NET Framework 3.0 или .NET Framework 3.5 в рабочем процессе .NET Framework 4.5
Действие <xref:System.Activities.Statements.Interop> позволяет выполнять действие .NET Framework 3.0 [!INCLUDE[wf](../../../../includes/wf-md.md)] в рабочем процессе [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].В этом образце показано, как использовать действие <xref:System.Activities.Statements.Interop> для передачи строки в качестве аргумента для пользовательского действия [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].  
  
## Использование этого образца  
  
1.  Используя [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], откройте файл решения SimpleInterop.sln.  
  
2.  Для построения решения нажмите CTRL\+SHIFT\+B.  
  
3.  Чтобы запустить решение, нажмите клавиши CTRL\+F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Basic\Migration\SimpleInterop`  
  
## См. также