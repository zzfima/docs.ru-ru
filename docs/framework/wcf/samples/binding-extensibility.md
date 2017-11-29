---
title: "Расширяемость привязок"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cabdd583-ddf5-493e-9dba-c6c31cde8f65
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 61c8ae647012c5f1fffe5cf65c63b64cde62af1b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="binding-extensibility"></a><span data-ttu-id="74cb8-102">Расширяемость привязок</span><span class="sxs-lookup"><span data-stu-id="74cb8-102">Binding Extensibility</span></span>
<span data-ttu-id="74cb8-103">Образцы в этом разделе демонстрируют пользовательскую привязку в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="74cb8-103">This section contains samples that demonstrate custom binding in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="74cb8-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="74cb8-104">In This Section</span></span>  
 <xref:System.ServiceModel.NetHttpBinding>  
 <span data-ttu-id="74cb8-105">Показывает, как реализовать привязку, которая размещает <xref:System.ServiceModel.Channels.HttpTransportBindingElement> или, <xref:System.ServiceModel.Channels.HttpsTransportBindingElement> поверх <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="74cb8-105">Demonstrates how to implement a binding that stacks <xref:System.ServiceModel.Channels.HttpTransportBindingElement> or the <xref:System.ServiceModel.Channels.HttpsTransportBindingElement> on top of the <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>.</span></span>  
  
 <!--zz <xref:System.ServiceModel.WSStreamedHttpBinding> --> `System.ServiceModel.WSStreamedHttpBinding` 
 <span data-ttu-id="74cb8-106">Демонстрация создания привязки, предназначенной для поддержки сценариев работы с потоками при использовании транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="74cb8-106">Demonstrates how to create a binding that is designed to support streaming scenarios when the HTTP transport is used.</span></span>
