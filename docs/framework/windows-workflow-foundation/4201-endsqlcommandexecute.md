---
title: 4201 - EndSqlCommandExecute
ms.date: 03/30/2017
ms.assetid: ae0dbc15-f98c-4096-a8d9-fbe4dc36f1cd
ms.openlocfilehash: 75c1cdd10aca6b177911bd9d2f51468016eb9e15
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774365"
---
# <a name="4201---endsqlcommandexecute"></a><span data-ttu-id="59c65-102">4201 - EndSqlCommandExecute</span><span class="sxs-lookup"><span data-stu-id="59c65-102">4201 - EndSqlCommandExecute</span></span>
## <a name="properties"></a><span data-ttu-id="59c65-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="59c65-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="59c65-104">ID</span><span class="sxs-lookup"><span data-stu-id="59c65-104">ID</span></span>|<span data-ttu-id="59c65-105">4201</span><span class="sxs-lookup"><span data-stu-id="59c65-105">4201</span></span>|  
|<span data-ttu-id="59c65-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="59c65-106">Keywords</span></span>|<span data-ttu-id="59c65-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="59c65-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="59c65-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="59c65-108">Level</span></span>|<span data-ttu-id="59c65-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="59c65-109">Verbose</span></span>|  
|<span data-ttu-id="59c65-110">Канал</span><span class="sxs-lookup"><span data-stu-id="59c65-110">Channel</span></span>|<span data-ttu-id="59c65-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="59c65-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="59c65-112">Описание</span><span class="sxs-lookup"><span data-stu-id="59c65-112">Description</span></span>  
 <span data-ttu-id="59c65-113">Указывает, что команда SQL завершена.</span><span class="sxs-lookup"><span data-stu-id="59c65-113">Indicates a SQL command has finished executing.</span></span>  
  
## <a name="message"></a><span data-ttu-id="59c65-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="59c65-114">Message</span></span>  
 <span data-ttu-id="59c65-115">Окончание выполнения команды SQL: %1</span><span class="sxs-lookup"><span data-stu-id="59c65-115">End SQL command execution: %1</span></span>  
  
## <a name="details"></a><span data-ttu-id="59c65-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="59c65-116">Details</span></span>  
  
|<span data-ttu-id="59c65-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="59c65-117">Data Item Name</span></span>|<span data-ttu-id="59c65-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="59c65-118">Data Item Type</span></span>|<span data-ttu-id="59c65-119">Описание</span><span class="sxs-lookup"><span data-stu-id="59c65-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="59c65-120">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="59c65-120">SqlCommand</span></span>|<span data-ttu-id="59c65-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="59c65-121">xs:string</span></span>|<span data-ttu-id="59c65-122">Команда SQL, которая была выполнена.</span><span class="sxs-lookup"><span data-stu-id="59c65-122">The SQL command that was executed.</span></span>|  
|<span data-ttu-id="59c65-123">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="59c65-123">AppDomain</span></span>|<span data-ttu-id="59c65-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="59c65-124">xs:string</span></span>|<span data-ttu-id="59c65-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="59c65-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
