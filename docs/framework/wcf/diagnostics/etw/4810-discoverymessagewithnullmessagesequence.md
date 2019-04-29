---
title: 4810 - DiscoveryMessageWithNullMessageSequence
ms.date: 03/30/2017
ms.assetid: aa70573e-8a76-486a-9616-ccca8c7008b6
ms.openlocfilehash: 371cd97d04b37796563b30273559bcaabb10fbba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778408"
---
# <a name="4810---discoverymessagewithnullmessagesequence"></a><span data-ttu-id="502d6-102">4810 - DiscoveryMessageWithNullMessageSequence</span><span class="sxs-lookup"><span data-stu-id="502d6-102">4810 - DiscoveryMessageWithNullMessageSequence</span></span>
## <a name="properties"></a><span data-ttu-id="502d6-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="502d6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="502d6-104">ID</span><span class="sxs-lookup"><span data-stu-id="502d6-104">ID</span></span>|<span data-ttu-id="502d6-105">4810</span><span class="sxs-lookup"><span data-stu-id="502d6-105">4810</span></span>|  
|<span data-ttu-id="502d6-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="502d6-106">Keywords</span></span>|<span data-ttu-id="502d6-107">Обнаружение</span><span class="sxs-lookup"><span data-stu-id="502d6-107">Discovery</span></span>|  
|<span data-ttu-id="502d6-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="502d6-108">Level</span></span>|<span data-ttu-id="502d6-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="502d6-109">Warning</span></span>|  
|<span data-ttu-id="502d6-110">Канал</span><span class="sxs-lookup"><span data-stu-id="502d6-110">Channel</span></span>|<span data-ttu-id="502d6-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="502d6-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="502d6-112">Описание</span><span class="sxs-lookup"><span data-stu-id="502d6-112">Description</span></span>  
 <span data-ttu-id="502d6-113">Это событие создается при отбрасывании клиентом DiscoveryClient сообщения запроса обнаружения из-за отсутствия в нем свойства DiscoveryMessageSequence.</span><span class="sxs-lookup"><span data-stu-id="502d6-113">This event is emitted when the discovery message was dropped by the DiscoveryClient because it did not have the DiscoveryMessageSequence property.</span></span>  
  
## <a name="message"></a><span data-ttu-id="502d6-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="502d6-114">Message</span></span>  
 <span data-ttu-id="502d6-115">Сообщение %1 с messageId="%2" удалено клиентом DiscoveryClient, поскольку в нем отсутствует свойство DiscoveryMessageSequence.</span><span class="sxs-lookup"><span data-stu-id="502d6-115">A %1 message with messageId='%2' was dropped by the DiscoveryClient because it did not have the DiscoveryMessageSequence property.</span></span>  
  
## <a name="details"></a><span data-ttu-id="502d6-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="502d6-116">Details</span></span>
