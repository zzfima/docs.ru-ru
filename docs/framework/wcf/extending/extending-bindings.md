---
title: "Расширение привязок"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: extending bindings [WCF]
ms.assetid: 5e40d306-b3c1-4429-80c4-fbb1d956856c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 692e51fc6276fbee0c1764c0040a251fe32b2c9f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="extending-bindings"></a><span data-ttu-id="db937-102">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="db937-102">Extending Bindings</span></span>
<span data-ttu-id="db937-103">Привязки задают транспорт, кодирование и протокол, необходимые для подключения к конечной точке.</span><span class="sxs-lookup"><span data-stu-id="db937-103">Bindings specify the transport, encoding, and protocol required to connect to an endpoint.</span></span> <span data-ttu-id="db937-104">Расширения привязки и пользовательские привязки реализуют пользовательскую функциональность связи, необходимую для поддержки возможностей приложения.</span><span class="sxs-lookup"><span data-stu-id="db937-104">Binding extensions and custom bindings implement custom communication functionality required to support application features.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="db937-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="db937-105">In This Section</span></span>  
  
|<span data-ttu-id="db937-106">Раздел</span><span class="sxs-lookup"><span data-stu-id="db937-106">Topic</span></span>|<span data-ttu-id="db937-107">Описание</span><span class="sxs-lookup"><span data-stu-id="db937-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="db937-108">Привязки и элементы привязки</span><span class="sxs-lookup"><span data-stu-id="db937-108">Bindings and Binding Elements</span></span>](../../../../docs/framework/wcf/extending/bindings-and-binding-elements.md)|<span data-ttu-id="db937-109">Описание привязок, элементов привязок, а также порядка их использования и расширения.</span><span class="sxs-lookup"><span data-stu-id="db937-109">Describes bindings, binding elements, and how they are used and extended.</span></span>|  
|[<span data-ttu-id="db937-110">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="db937-110">Custom Bindings</span></span>](../../../../docs/framework/wcf/extending/custom-bindings.md)|<span data-ttu-id="db937-111">Описание порядка использования класса <xref:System.ServiceModel.Channels.CustomBinding> для создания пользовательских привязок с помощью элементов привязки, определенных системой и предоставляемых независимыми разработчиками.</span><span class="sxs-lookup"><span data-stu-id="db937-111">Describes how to use the <xref:System.ServiceModel.Channels.CustomBinding> class to create custom bindings using system-defined and third-party binding elements.</span></span>|  
|[<span data-ttu-id="db937-112">Создание пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="db937-112">Creating User-Defined Bindings</span></span>](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md)|<span data-ttu-id="db937-113">Описание порядка создания привязок и элементов привязок для использования другими разработчиками.</span><span class="sxs-lookup"><span data-stu-id="db937-113">Describes how to create bindings and binding elements that can be used by others.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="db937-114">Ссылка</span><span class="sxs-lookup"><span data-stu-id="db937-114">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="db937-115">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="db937-115">Related Sections</span></span>  
 [<span data-ttu-id="db937-116">Создание элемента привязки BindingElement</span><span class="sxs-lookup"><span data-stu-id="db937-116">Creating a BindingElement</span></span>](../../../../docs/framework/wcf/extending/creating-a-bindingelement.md)  
  
 [<span data-ttu-id="db937-117">Конфигурация и поддержка метаданных</span><span class="sxs-lookup"><span data-stu-id="db937-117">Configuration and Metadata Support</span></span>](../../../../docs/framework/wcf/extending/configuration-and-metadata-support.md)
