---
title: "Расширение привязок"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- extending bindings [WCF]
ms.assetid: 5e40d306-b3c1-4429-80c4-fbb1d956856c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5d0be5e799137d24c2d6e53f4b6846007f3a2a79
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="extending-bindings"></a><span data-ttu-id="6f7ed-102">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="6f7ed-102">Extending Bindings</span></span>
<span data-ttu-id="6f7ed-103">Привязки задают транспорт, кодирование и протокол, необходимые для подключения к конечной точке.</span><span class="sxs-lookup"><span data-stu-id="6f7ed-103">Bindings specify the transport, encoding, and protocol required to connect to an endpoint.</span></span> <span data-ttu-id="6f7ed-104">Расширения привязки и пользовательские привязки реализуют пользовательскую функциональность связи, необходимую для поддержки возможностей приложения.</span><span class="sxs-lookup"><span data-stu-id="6f7ed-104">Binding extensions and custom bindings implement custom communication functionality required to support application features.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6f7ed-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="6f7ed-105">In This Section</span></span>  
  
|<span data-ttu-id="6f7ed-106">Раздел</span><span class="sxs-lookup"><span data-stu-id="6f7ed-106">Topic</span></span>|<span data-ttu-id="6f7ed-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="6f7ed-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="6f7ed-108">Привязки и элементы привязки</span><span class="sxs-lookup"><span data-stu-id="6f7ed-108">Bindings and Binding Elements</span></span>](../../../../docs/framework/wcf/extending/bindings-and-binding-elements.md)|<span data-ttu-id="6f7ed-109">Описание привязок, элементов привязок, а также порядка их использования и расширения.</span><span class="sxs-lookup"><span data-stu-id="6f7ed-109">Describes bindings, binding elements, and how they are used and extended.</span></span>|  
|[<span data-ttu-id="6f7ed-110">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="6f7ed-110">Custom Bindings</span></span>](../../../../docs/framework/wcf/extending/custom-bindings.md)|<span data-ttu-id="6f7ed-111">Описание порядка использования класса <xref:System.ServiceModel.Channels.CustomBinding> для создания пользовательских привязок с помощью элементов привязки, определенных системой и предоставляемых независимыми разработчиками.</span><span class="sxs-lookup"><span data-stu-id="6f7ed-111">Describes how to use the <xref:System.ServiceModel.Channels.CustomBinding> class to create custom bindings using system-defined and third-party binding elements.</span></span>|  
|[<span data-ttu-id="6f7ed-112">Создание пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="6f7ed-112">Creating User-Defined Bindings</span></span>](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md)|<span data-ttu-id="6f7ed-113">Описание порядка создания привязок и элементов привязок для использования другими разработчиками.</span><span class="sxs-lookup"><span data-stu-id="6f7ed-113">Describes how to create bindings and binding elements that can be used by others.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="6f7ed-114">Ссылка</span><span class="sxs-lookup"><span data-stu-id="6f7ed-114">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6f7ed-115">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="6f7ed-115">Related Sections</span></span>  
 [<span data-ttu-id="6f7ed-116">Создание элемента привязки BindingElement</span><span class="sxs-lookup"><span data-stu-id="6f7ed-116">Creating a BindingElement</span></span>](../../../../docs/framework/wcf/extending/creating-a-bindingelement.md)  
  
 [<span data-ttu-id="6f7ed-117">Конфигурация и поддержка метаданных</span><span class="sxs-lookup"><span data-stu-id="6f7ed-117">Configuration and Metadata Support</span></span>](../../../../docs/framework/wcf/extending/configuration-and-metadata-support.md)
