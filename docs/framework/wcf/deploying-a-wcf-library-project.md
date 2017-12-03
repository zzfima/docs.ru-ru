---
title: "Развертывание проекта библиотеки WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f9222fe-d358-443c-9a49-12c5498e35e7
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dbddd99125e8615640ca39d091e92cdde87c9faf
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="deploying-a-wcf-library-project"></a>Развертывание проекта библиотеки WCF
В данном разделе описывается развертывание проекта библиотеки службы [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].  
  
## <a name="deploying-a-wcf-service-library"></a>Развертывание библиотеки службы WCF  
 Библиотека службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] - это динамически подключаемая библиотека (DLL). Поэтому она не может выполняться сама по себе. Ее необходимо развернуть в среде размещения. Дополнительные сведения об этом процессе см. в разделе [размещение и использование служб WCF](http://go.microsoft.com/fwlink/?LinkId=99932).  
  
 Библиотека службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] может быть развернута как любая другая служба [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Однако следует помнить, что [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] не поддерживает конфигурацию для DLL-библиотек. <xref:System.Configuration> поддерживает один файл конфигурации на домен приложений. Проект библиотеки служб [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] снимает это ограничение путем предоставления файла App.config для библиотеки при развертывании. Однако файл App.config после развертывания не распознается.  
  
 Необходимо переместить код конфигурации в файл конфигурации, который распознается средой размещения. Для резидентного размещения необходимо скопировать содержимое файла App.config в файл App.config исполняемого файла размещения. Если для размещения службы используется узел IIS, то необходимо копировать содержимое файла App.config в файл Web.config виртуального каталога.
