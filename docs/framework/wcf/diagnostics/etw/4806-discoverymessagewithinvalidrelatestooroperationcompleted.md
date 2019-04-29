---
title: 4806 - DiscoveryMessageWithInvalidRelatesToOrOperationCompleted
ms.date: 03/30/2017
ms.assetid: 19e9a660-25f3-4332-b716-a12a59f2cbbb
ms.openlocfilehash: 3d0d8d426b0b8b7e5a1e890847ae36957e62f028
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61943043"
---
# <a name="4806---discoverymessagewithinvalidrelatestooroperationcompleted"></a><span data-ttu-id="fed9c-102">4806 - DiscoveryMessageWithInvalidRelatesToOrOperationCompleted</span><span class="sxs-lookup"><span data-stu-id="fed9c-102">4806 - DiscoveryMessageWithInvalidRelatesToOrOperationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="fed9c-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="fed9c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fed9c-104">ID</span><span class="sxs-lookup"><span data-stu-id="fed9c-104">ID</span></span>|<span data-ttu-id="fed9c-105">4806</span><span class="sxs-lookup"><span data-stu-id="fed9c-105">4806</span></span>|  
|<span data-ttu-id="fed9c-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="fed9c-106">Keywords</span></span>|<span data-ttu-id="fed9c-107">Обнаружение</span><span class="sxs-lookup"><span data-stu-id="fed9c-107">Discovery</span></span>|  
|<span data-ttu-id="fed9c-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="fed9c-108">Level</span></span>|<span data-ttu-id="fed9c-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="fed9c-109">Warning</span></span>|  
|<span data-ttu-id="fed9c-110">Канал</span><span class="sxs-lookup"><span data-stu-id="fed9c-110">Channel</span></span>|<span data-ttu-id="fed9c-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="fed9c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fed9c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="fed9c-112">Description</span></span>  
 <span data-ttu-id="fed9c-113">Это сообщение создается, если сообщение обнаружения было отброшено клиентом DiscoveryClient, поскольку выполнена соответствующая операция, либо значение relatesTo является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="fed9c-113">This event is emitted when the discovery message was dropped by the DiscoveryClient because either the corresponding operation was completed or the relatesTo value is invalid.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fed9c-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="fed9c-114">Message</span></span>  
 <span data-ttu-id="fed9c-115">Сообщение %1 с messageId="%2" и relatesTo="%3" удалено клиентом DiscoveryClient, поскольку выполнена соответствующая операция %4 или значение relatesTo является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="fed9c-115">A %1 message with messageId='%2' and relatesTo='%3' was dropped by the DiscoveryClient because either the corresponding %4 operation was completed or the relatesTo value is invalid.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fed9c-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="fed9c-116">Details</span></span>
