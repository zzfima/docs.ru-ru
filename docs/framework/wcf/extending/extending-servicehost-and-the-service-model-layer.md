---
title: "Расширение ServiceHost и уровень модели службы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: extending service models [WCF]
ms.assetid: 954c138a-1cd0-45a0-8abe-e4d2b8ff5400
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 67ed4be3211af141af87da2406e81ff5e2fbb767
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="extending-servicehost-and-the-service-model-layer"></a>Расширение ServiceHost и уровень модели службы
Уровень модели службы отвечает за удаление входящих сообщений из базовых каналов, их перевод в вызовы метода в коде приложения и отправку результатов обратно вызывающему коду. Расширения модели службы изменяют или реализуют поведение и возможности выполнения или взаимодействия, в том числе возможности клиента или диспетчера, пользовательские поведения, перехват сообщений и параметров, а также другие возможности расширяемости.  
  
## <a name="in-this-section"></a>Содержание  
 [Расширение клиентов](../../../../docs/framework/wcf/extending/extending-clients.md)  
 Описываются интерфейсы, которые могут перехватывать и изменять среду выполнения клиента, а также классы, в которые можно вставить специальные расширения в клиентских приложениях. Например, можно выполнять специальную регистрацию сообщений, специальную сериализацию сообщений и т. п.  
  
 [Расширение диспетчеров](../../../../docs/framework/wcf/extending/extending-dispatchers.md)  
 Описываются интерфейсы, которые могут перехватывать и изменять среду выполнения службы, а также классы, в которые можно вставить пользовательские расширения в приложениях служб. Например, можно выполнять специальную регистрацию службы, проверку сообщений со стороны службы, специальную диспетчеризацию и т. п.  
  
 [Расширяемые объекты](../../../../docs/framework/wcf/extending/extensible-objects.md)  
 Описывается пять расширяемых объектов и шаблон <xref:System.ServiceModel.IExtensibleObject%601>. Шаблон расширяемого объекта используется для расширения существующих классов среды выполнения при помощи новых функций или добавления нового состояния к объекту. Расширения, привязанные к одному из расширяемых объектов, позволяют использовать поведения на различных этапах обработки для получения доступа к общему состоянию и функциональности, привязанным к общему расширяемому объекту, к которому они могут получить доступ.  
  
 [Настройка и расширение среды выполнения с помощью поведений](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)  
 Для изменения параметров или вставки расширений в среду выполнения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] используются поведения. WCF включает реализованные системой поведения для контроля регулирования количества запросов, использования экземпляров и многих других аспектов, относящихся к службам и операциям. В данном разделе описывается, как создавать собственные пользовательские поведения и как обеспечить их доступность как программными средствами, так и при помощи файлов конфигурации.  
  
 [Расширение размещения с использованием ServiceHostFactory](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)  
 Описывается, как расширить <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType>, <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> и использовать классы <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=nameWithType> с целью настройки среды узла.  
  
## <a name="reference"></a>Ссылка  
  
## <a name="related-sections"></a>Связанные разделы
