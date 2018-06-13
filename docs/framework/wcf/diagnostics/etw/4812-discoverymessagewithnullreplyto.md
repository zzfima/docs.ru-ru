---
title: 4812 - DiscoveryMessageWithNullReplyTo
ms.date: 03/30/2017
ms.assetid: a40e6b7e-c2a6-4186-b1d6-c9560f24a959
ms.openlocfilehash: ff281dc7fe5dd277d9cd69cdea51bd155cc79546
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33472087"
---
# <a name="4812---discoverymessagewithnullreplyto"></a><span data-ttu-id="02b1d-102">4812 - DiscoveryMessageWithNullReplyTo</span><span class="sxs-lookup"><span data-stu-id="02b1d-102">4812 - DiscoveryMessageWithNullReplyTo</span></span>
## <a name="properties"></a><span data-ttu-id="02b1d-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="02b1d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="02b1d-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="02b1d-104">ID</span></span>|<span data-ttu-id="02b1d-105">4812</span><span class="sxs-lookup"><span data-stu-id="02b1d-105">4812</span></span>|  
|<span data-ttu-id="02b1d-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="02b1d-106">Keywords</span></span>|<span data-ttu-id="02b1d-107">Обнаружение</span><span class="sxs-lookup"><span data-stu-id="02b1d-107">Discovery</span></span>|  
|<span data-ttu-id="02b1d-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="02b1d-108">Level</span></span>|<span data-ttu-id="02b1d-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="02b1d-109">Warning</span></span>|  
|<span data-ttu-id="02b1d-110">Канал</span><span class="sxs-lookup"><span data-stu-id="02b1d-110">Channel</span></span>|<span data-ttu-id="02b1d-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="02b1d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="02b1d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="02b1d-112">Description</span></span>  
 <span data-ttu-id="02b1d-113">Это событие создается при удалении клиентом DiscoveryClient сообщения запроса обнаружения из-за отсутствия в нем адреса ReplyTo.</span><span class="sxs-lookup"><span data-stu-id="02b1d-113">This event is emitted when the discovery message was dropped by the DiscoveryClient because it did not have a ReplyTo address.</span></span>  
  
## <a name="message"></a><span data-ttu-id="02b1d-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="02b1d-114">Message</span></span>  
 <span data-ttu-id="02b1d-115">Сообщение запроса обнаружения с messageId="%1" удалено, поскольку отсутствует адрес ReplyTo.</span><span class="sxs-lookup"><span data-stu-id="02b1d-115">A discovery request message with messageId='%1' was dropped because it did not have a ReplyTo address.</span></span>  
  
## <a name="details"></a><span data-ttu-id="02b1d-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="02b1d-116">Details</span></span>
