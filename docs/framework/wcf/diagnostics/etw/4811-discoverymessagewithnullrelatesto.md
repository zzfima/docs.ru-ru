---
title: 4811 - DiscoveryMessageWithNullRelatesTo
ms.date: 03/30/2017
ms.assetid: dab901e8-a2b3-41c1-a76b-bcd8b3c7c29a
ms.openlocfilehash: 74ce12656d0cfd994cb3b0ea1021405a89a30751
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62040052"
---
# <a name="4811---discoverymessagewithnullrelatesto"></a><span data-ttu-id="31560-102">4811 - DiscoveryMessageWithNullRelatesTo</span><span class="sxs-lookup"><span data-stu-id="31560-102">4811 - DiscoveryMessageWithNullRelatesTo</span></span>
## <a name="properties"></a><span data-ttu-id="31560-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="31560-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="31560-104">ID</span><span class="sxs-lookup"><span data-stu-id="31560-104">ID</span></span>|<span data-ttu-id="31560-105">4811</span><span class="sxs-lookup"><span data-stu-id="31560-105">4811</span></span>|  
|<span data-ttu-id="31560-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="31560-106">Keywords</span></span>|<span data-ttu-id="31560-107">Обнаружение</span><span class="sxs-lookup"><span data-stu-id="31560-107">Discovery</span></span>|  
|<span data-ttu-id="31560-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="31560-108">Level</span></span>|<span data-ttu-id="31560-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="31560-109">Warning</span></span>|  
|<span data-ttu-id="31560-110">Канал</span><span class="sxs-lookup"><span data-stu-id="31560-110">Channel</span></span>|<span data-ttu-id="31560-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="31560-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="31560-112">Описание</span><span class="sxs-lookup"><span data-stu-id="31560-112">Description</span></span>  
 <span data-ttu-id="31560-113">Это событие создается при отбрасывании сообщения обнаружения объектом DiscoveryClient из-за отсутствия в заголовке сообщения обязательного свойства RelatesTo.</span><span class="sxs-lookup"><span data-stu-id="31560-113">This event is emitted when the discovery message was dropped by the DiscoveryClient because the message header did not contain the required RelatesTo property.</span></span>  
  
## <a name="message"></a><span data-ttu-id="31560-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="31560-114">Message</span></span>  
 <span data-ttu-id="31560-115">Сообщение %1 с messageId="%2" удалено клиентом DiscoveryClient, поскольку заголовок сообщения не содержит обязательного свойства RelatesTo.</span><span class="sxs-lookup"><span data-stu-id="31560-115">A %1 message with messageId='%2' was dropped by the DiscoveryClient because the message header did not contain the required RelatesTo property.</span></span>  
  
## <a name="details"></a><span data-ttu-id="31560-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="31560-116">Details</span></span>
