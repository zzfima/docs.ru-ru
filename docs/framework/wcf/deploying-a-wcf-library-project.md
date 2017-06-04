---
title: "Развертывание проекта библиотеки WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9f9222fe-d358-443c-9a49-12c5498e35e7
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Развертывание проекта библиотеки WCF
В данном разделе описывается развертывание проекта библиотеки службы [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].  
  
## Развертывание библиотеки службы WCF  
 Библиотека службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] — это динамически подключаемая библиотека \(DLL\).Поэтому она не может выполняться сама по себе.Ее необходимо развернуть в среде размещения.Дополнительные сведения об этом процессе см.[Создание и обращение к службам WCF](http://go.microsoft.com/fwlink/?LinkId=99932).  
  
 Библиотека службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] может быть развернута как любая другая служба [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].Однако следует помнить, что [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] не поддерживает конфигурацию для DLL\-библиотек.<xref:System.Configuration> поддерживает один файл конфигурации на домен приложения.Проект библиотеки служб [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] снимает это ограничение путем предоставления файла App.config для библиотеки при развертывании.Однако файл App.config после развертывания не распознается.  
  
 Необходимо переместить код конфигурации в файл конфигурации, который распознается средой размещения.Для резидентного размещения необходимо скопировать содержимое файла App.config в файл App.config исполняемого файла размещения.Если для размещения службы используется узел IIS, то необходимо копировать содержимое файла App.config в файл Web.config виртуального каталога.