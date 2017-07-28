---
title: "Управление автозапуском узла службы WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "WcfOptions"
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Управление автозапуском узла службы WCF
Можно управлять возможностью автозапуска узла службы [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] \(WcfSvcHost.exe\) для проекта библиотеки службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] при отладке другого проекта в одном решении [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], которое содержит несколько проектов.  
  
 Для этого щелкните правой кнопкой мыши проект службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] в **Обозревателе решений**, выберите **Свойства** и перейдите на вкладку **Параметры WCF**.По умолчанию флажок **Запуск узла службы WCF при отладке другого проекта в одном решении** установлен.Вы можете снять флажок, чтобы узел службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] не запускался для заданного проекта при отладке \(в том же решении\) другого проекта.  
  
 Это поведение не оказывает влияние на отладку по клавише F5 или на функциональные возможности добавления ссылки на службу для этого проекта.  
  
 Эта возможность доступна в следующих проектах.  
  
-   Проект библиотеки служб [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
-   Проект библиотеки службы последовательного рабочего процесса.  
  
-   Проект библиотеки рабочего процесса конечного автомата.  
  
-   Проект библиотеки служб синдикации.  
  
## См. также  
 [Узел службы WCF \(WcfSvcHost.exe\)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)