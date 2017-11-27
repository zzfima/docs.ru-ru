---
title: "Привязка безопасности сообщений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a4570ce7-864e-461b-85d8-0f7bcc53c2c8
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: ca1ce99fae09ef7d3c9ad3ea47984b671cadb27c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="message-security-binding"></a><span data-ttu-id="48888-102">Привязка безопасности сообщений</span><span class="sxs-lookup"><span data-stu-id="48888-102">Message Security Binding</span></span>
<span data-ttu-id="48888-103">Данный раздел содержит образцы, которые демонстрируют привязку безопасности сообщений в службах Windows в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48888-103">This section contains samples that demonstrate message security binding in Windows Services in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="48888-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="48888-104">In This Section</span></span>  
 [<span data-ttu-id="48888-105">Анонимного обеспечения безопасности сообщений</span><span class="sxs-lookup"><span data-stu-id="48888-105">Message Security Anonymous</span></span>](../../../../docs/framework/wcf/samples/message-security-anonymous.md)  
 <span data-ttu-id="48888-106">В этом образце показана реализация приложения [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] с использованием безопасности уровня сообщений, без проверки подлинности клиента, но с требованием проверки подлинности сервера с помощью сертификата X.509 для сервера.</span><span class="sxs-lookup"><span data-stu-id="48888-106">This sample demonstrates how to implement a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] application that uses message-level security with no client authentication but that requires server authentication using the server's X.509 certificate.</span></span>  
  
 [<span data-ttu-id="48888-107">Сертификат безопасности сообщений</span><span class="sxs-lookup"><span data-stu-id="48888-107">Message Security Certificate</span></span>](../../../../docs/framework/wcf/samples/message-security-certificate.md)  
 <span data-ttu-id="48888-108">В этом образце показано, как реализовать приложение, использующее протокол WS-Security и проверку подлинности с использованием сертификата X.509 v3 для клиента и требующее проверки подлинности сервера с использованием сертификата X.509 v3 сервера.</span><span class="sxs-lookup"><span data-stu-id="48888-108">This sample demonstrates how to implement an application that uses WS-Security with X.509 v3 certificate authentication for the client and requires server authentication using the server's X.509 v3 certificate.</span></span>  
  
 [<span data-ttu-id="48888-109">Имя пользователя для безопасности сообщений</span><span class="sxs-lookup"><span data-stu-id="48888-109">Message Security User Name</span></span>](../../../../docs/framework/wcf/samples/message-security-user-name.md)  
 <span data-ttu-id="48888-110">В этом образце показано, как реализовать приложение, использующее протокол WS-Security и проверку подлинности имен пользователя для клиента и требующее проверки подлинности сервера с использованием сертификата X.509v3 сервера.</span><span class="sxs-lookup"><span data-stu-id="48888-110">This sample demonstrates how to implement an application that uses WS-Security with username authentication for the client and requires server authentication using the server's X.509v3 certificate.</span></span>  
  
 [<span data-ttu-id="48888-111">Сообщение безопасности Windows</span><span class="sxs-lookup"><span data-stu-id="48888-111">Message Security Windows</span></span>](../../../../docs/framework/wcf/samples/message-security-windows.md)  
 <span data-ttu-id="48888-112">В этом образце показывается, как настраивать привязку <xref:System.ServiceModel.WSHttpBinding> для использования безопасности на уровне сообщений с проверкой подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="48888-112">This sample demonstrates how to configure a <xref:System.ServiceModel.WSHttpBinding> binding to use message-level security with Windows authentication.</span></span>
