---
title: Развертывание проекта библиотеки WCF
ms.date: 03/30/2017
ms.assetid: 9f9222fe-d358-443c-9a49-12c5498e35e7
ms.openlocfilehash: 08a1d794aeeea1a41cd1eb3abf298f3f4a0f6d15
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="deploying-a-wcf-library-project"></a>Развертывание проекта библиотеки WCF
В этом разделе описано, как развернуть проект библиотеки службы Windows Communication Foundation (WCF).  
  
## <a name="deploying-a-wcf-service-library"></a>Развертывание библиотеки службы WCF  
 Библиотека службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] - это динамически подключаемая библиотека (DLL). Поэтому она не может выполняться сама по себе. Ее необходимо развернуть в среде размещения. Дополнительные сведения об этом процессе см. в разделе [размещение и использование служб WCF](http://go.microsoft.com/fwlink/?LinkId=99932).  
  
 Библиотека службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] может быть развернута как любая другая служба [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Однако следует помнить, что [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] не поддерживает конфигурацию для DLL-библиотек. <xref:System.Configuration> поддерживает один файл конфигурации на домен приложений. Проект библиотеки служб [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] снимает это ограничение путем предоставления файла App.config для библиотеки при развертывании. Однако файл App.config после развертывания не распознается.  
  
 Необходимо переместить код конфигурации в файл конфигурации, который распознается средой размещения. Для резидентного размещения необходимо скопировать содержимое файла App.config в файл App.config исполняемого файла размещения. Если для размещения службы используется узел IIS, то необходимо копировать содержимое файла App.config в файл Web.config виртуального каталога.
