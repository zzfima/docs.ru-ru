---
title: 4806 - DiscoveryMessageWithInvalidRelatesToOrOperationCompleted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19e9a660-25f3-4332-b716-a12a59f2cbbb
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2760ebaee26085bfaa4c4de2d14b41ba0d70fdf0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="4806---discoverymessagewithinvalidrelatestooroperationcompleted"></a><span data-ttu-id="04bdb-102">4806 - DiscoveryMessageWithInvalidRelatesToOrOperationCompleted</span><span class="sxs-lookup"><span data-stu-id="04bdb-102">4806 - DiscoveryMessageWithInvalidRelatesToOrOperationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="04bdb-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="04bdb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="04bdb-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="04bdb-104">ID</span></span>|<span data-ttu-id="04bdb-105">4806</span><span class="sxs-lookup"><span data-stu-id="04bdb-105">4806</span></span>|  
|<span data-ttu-id="04bdb-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="04bdb-106">Keywords</span></span>|<span data-ttu-id="04bdb-107">Обнаружение</span><span class="sxs-lookup"><span data-stu-id="04bdb-107">Discovery</span></span>|  
|<span data-ttu-id="04bdb-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="04bdb-108">Level</span></span>|<span data-ttu-id="04bdb-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="04bdb-109">Warning</span></span>|  
|<span data-ttu-id="04bdb-110">Канал</span><span class="sxs-lookup"><span data-stu-id="04bdb-110">Channel</span></span>|<span data-ttu-id="04bdb-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="04bdb-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="04bdb-112">Описание</span><span class="sxs-lookup"><span data-stu-id="04bdb-112">Description</span></span>  
 <span data-ttu-id="04bdb-113">Это сообщение создается, если сообщение обнаружения было удалено клиентом DiscoveryClient, поскольку выполнена соответствующая операция, либо значение relatesTo является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="04bdb-113">This event is emitted when the discovery message was dropped by the DiscoveryClient because either the corresponding operation was completed or the relatesTo value is invalid.</span></span>  
  
## <a name="message"></a><span data-ttu-id="04bdb-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="04bdb-114">Message</span></span>  
 <span data-ttu-id="04bdb-115">Сообщение %1 с messageId="%2" и relatesTo="%3" удалено клиентом DiscoveryClient, поскольку выполнена соответствующая операция %4 или значение relatesTo является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="04bdb-115">A %1 message with messageId='%2' and relatesTo='%3' was dropped by the DiscoveryClient because either the corresponding %4 operation was completed or the relatesTo value is invalid.</span></span>  
  
## <a name="details"></a><span data-ttu-id="04bdb-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="04bdb-116">Details</span></span>
