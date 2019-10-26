---
title: Ресурсы операционной системы, необходимые WCF
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: c2c26d769424a8d0655591cb10b4b13df8a15884
ms.sourcegitcommit: 9b2ef64c4fc10a4a10f28a223d60d17d7d249ee8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/26/2019
ms.locfileid: "72961134"
---
# <a name="operating-system-resources-required-by-wcf"></a><span data-ttu-id="7112e-102">Ресурсы операционной системы, необходимые WCF</span><span class="sxs-lookup"><span data-stu-id="7112e-102">Operating System Resources Required by WCF</span></span>

<span data-ttu-id="7112e-103">Windows Communication Foundation (WCF) зависит от нескольких ресурсов, предоставляемых операционной системой для работы.</span><span class="sxs-lookup"><span data-stu-id="7112e-103">Windows Communication Foundation (WCF) depends on several resources that are provided by the operating system to function.</span></span> <span data-ttu-id="7112e-104">В следующей таблице перечислены эти ресурсы.</span><span class="sxs-lookup"><span data-stu-id="7112e-104">The following table lists those resources:</span></span>

|<span data-ttu-id="7112e-105">Ресурс</span><span class="sxs-lookup"><span data-stu-id="7112e-105">Resource</span></span>|<span data-ttu-id="7112e-106">Описание</span><span class="sxs-lookup"><span data-stu-id="7112e-106">Description</span></span>|
|--------------|-----------------|
|<span data-ttu-id="7112e-107">Координатор распределенных транзакций (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="7112e-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span></span>|<span data-ttu-id="7112e-108">Требуется для поддержки транзакций OleTx.</span><span class="sxs-lookup"><span data-stu-id="7112e-108">Required to support OleTx transactions.</span></span>|
|<span data-ttu-id="7112e-109">службы IIS</span><span class="sxs-lookup"><span data-stu-id="7112e-109">Internet Information Services (IIS)</span></span>|<span data-ttu-id="7112e-110">Требуется, если необходимо использовать службы IIS для размещения приложения.</span><span class="sxs-lookup"><span data-stu-id="7112e-110">Required if you want to use IIS to host your application.</span></span>|
|<span data-ttu-id="7112e-111">Служба активации Windows (WAS)</span><span class="sxs-lookup"><span data-stu-id="7112e-111">Windows Process Activation Service (WAS)</span></span>|<span data-ttu-id="7112e-112">Требуется, если необходимо использовать WAS для размещения приложения.</span><span class="sxs-lookup"><span data-stu-id="7112e-112">Required if you want to use WAS to host your application.</span></span>|
