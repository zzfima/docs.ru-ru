---
title: 4811 - DiscoveryMessageWithNullRelatesTo
ms.date: 03/30/2017
ms.assetid: dab901e8-a2b3-41c1-a76b-bcd8b3c7c29a
ms.openlocfilehash: 74ce12656d0cfd994cb3b0ea1021405a89a30751
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="4811---discoverymessagewithnullrelatesto"></a><span data-ttu-id="45cd5-102">4811 - DiscoveryMessageWithNullRelatesTo</span><span class="sxs-lookup"><span data-stu-id="45cd5-102">4811 - DiscoveryMessageWithNullRelatesTo</span></span>
## <a name="properties"></a><span data-ttu-id="45cd5-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="45cd5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="45cd5-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="45cd5-104">ID</span></span>|<span data-ttu-id="45cd5-105">4811</span><span class="sxs-lookup"><span data-stu-id="45cd5-105">4811</span></span>|  
|<span data-ttu-id="45cd5-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="45cd5-106">Keywords</span></span>|<span data-ttu-id="45cd5-107">Обнаружение</span><span class="sxs-lookup"><span data-stu-id="45cd5-107">Discovery</span></span>|  
|<span data-ttu-id="45cd5-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="45cd5-108">Level</span></span>|<span data-ttu-id="45cd5-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="45cd5-109">Warning</span></span>|  
|<span data-ttu-id="45cd5-110">Канал</span><span class="sxs-lookup"><span data-stu-id="45cd5-110">Channel</span></span>|<span data-ttu-id="45cd5-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="45cd5-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="45cd5-112">Описание</span><span class="sxs-lookup"><span data-stu-id="45cd5-112">Description</span></span>  
 <span data-ttu-id="45cd5-113">Это событие создается при удалении сообщения обнаружения объектом DiscoveryClient из-за отсутствия в заголовке сообщения обязательного свойства RelatesTo.</span><span class="sxs-lookup"><span data-stu-id="45cd5-113">This event is emitted when the discovery message was dropped by the DiscoveryClient because the message header did not contain the required RelatesTo property.</span></span>  
  
## <a name="message"></a><span data-ttu-id="45cd5-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="45cd5-114">Message</span></span>  
 <span data-ttu-id="45cd5-115">Сообщение %1 с messageId="%2" удалено клиентом DiscoveryClient, поскольку заголовок сообщения не содержит обязательного свойства RelatesTo.</span><span class="sxs-lookup"><span data-stu-id="45cd5-115">A %1 message with messageId='%2' was dropped by the DiscoveryClient because the message header did not contain the required RelatesTo property.</span></span>  
  
## <a name="details"></a><span data-ttu-id="45cd5-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="45cd5-116">Details</span></span>
