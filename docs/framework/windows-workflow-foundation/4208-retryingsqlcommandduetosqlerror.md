---
title: 4208 - RetryingSqlCommandDueToSqlError
ms.date: 03/30/2017
ms.assetid: a8e6483a-a6e4-4bbf-82ec-cd8b6e711aad
ms.openlocfilehash: a97336f12ccfe041b79328bcb48f4e7214a05b63
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a><span data-ttu-id="55433-102">4208 - RetryingSqlCommandDueToSqlError</span><span class="sxs-lookup"><span data-stu-id="55433-102">4208 - RetryingSqlCommandDueToSqlError</span></span>
## <a name="properties"></a><span data-ttu-id="55433-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="55433-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="55433-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="55433-104">ID</span></span>|<span data-ttu-id="55433-105">4208</span><span class="sxs-lookup"><span data-stu-id="55433-105">4208</span></span>|  
|<span data-ttu-id="55433-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="55433-106">Keywords</span></span>|<span data-ttu-id="55433-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="55433-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="55433-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="55433-108">Level</span></span>|<span data-ttu-id="55433-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="55433-109">Information</span></span>|  
|<span data-ttu-id="55433-110">Канал</span><span class="sxs-lookup"><span data-stu-id="55433-110">Channel</span></span>|<span data-ttu-id="55433-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="55433-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="55433-112">Описание</span><span class="sxs-lookup"><span data-stu-id="55433-112">Description</span></span>  
 <span data-ttu-id="55433-113">Указывает, что поставщик SQL повторяет команду SQL из-за ошибки SQL.</span><span class="sxs-lookup"><span data-stu-id="55433-113">Indicates the SQL provider is retrying a SQL command due to a SQL error.</span></span>  
  
## <a name="message"></a><span data-ttu-id="55433-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="55433-114">Message</span></span>  
 <span data-ttu-id="55433-115">Выполняется повтор команды SQL из-за ошибки SQL с номером %1.</span><span class="sxs-lookup"><span data-stu-id="55433-115">Retrying a SQL command due to SQL error number %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="55433-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="55433-116">Details</span></span>  
  
|<span data-ttu-id="55433-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="55433-117">Data Item Name</span></span>|<span data-ttu-id="55433-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="55433-118">Data Item Type</span></span>|<span data-ttu-id="55433-119">Описание</span><span class="sxs-lookup"><span data-stu-id="55433-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="55433-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="55433-120">ErrorNumber</span></span>|<span data-ttu-id="55433-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="55433-121">xs:string</span></span>|<span data-ttu-id="55433-122">Номер ошибки SQL.</span><span class="sxs-lookup"><span data-stu-id="55433-122">The SQL error number.</span></span>|  
|<span data-ttu-id="55433-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="55433-123">AppDomain</span></span>|<span data-ttu-id="55433-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="55433-124">xs:string</span></span>|<span data-ttu-id="55433-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="55433-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
