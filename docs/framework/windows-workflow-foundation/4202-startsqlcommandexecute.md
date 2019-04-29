---
title: 4202 - StartSqlCommandExecute
ms.date: 03/30/2017
ms.assetid: 4559f64f-c824-4075-9e7e-4710bf30f805
ms.openlocfilehash: 09e079864369115c773c58c451fc5e0a33a3ae9f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774378"
---
# <a name="4202---startsqlcommandexecute"></a><span data-ttu-id="11c90-102">4202 - StartSqlCommandExecute</span><span class="sxs-lookup"><span data-stu-id="11c90-102">4202 - StartSqlCommandExecute</span></span>
## <a name="properties"></a><span data-ttu-id="11c90-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="11c90-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="11c90-104">ID</span><span class="sxs-lookup"><span data-stu-id="11c90-104">ID</span></span>|<span data-ttu-id="11c90-105">4202</span><span class="sxs-lookup"><span data-stu-id="11c90-105">4202</span></span>|  
|<span data-ttu-id="11c90-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="11c90-106">Keywords</span></span>|<span data-ttu-id="11c90-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="11c90-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="11c90-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="11c90-108">Level</span></span>|<span data-ttu-id="11c90-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="11c90-109">Verbose</span></span>|  
|<span data-ttu-id="11c90-110">Канал</span><span class="sxs-lookup"><span data-stu-id="11c90-110">Channel</span></span>|<span data-ttu-id="11c90-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="11c90-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="11c90-112">Описание</span><span class="sxs-lookup"><span data-stu-id="11c90-112">Description</span></span>  
 <span data-ttu-id="11c90-113">Указывает, что команда SQL выполняется.</span><span class="sxs-lookup"><span data-stu-id="11c90-113">Indicates a SQL command is being executed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="11c90-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="11c90-114">Message</span></span>  
 <span data-ttu-id="11c90-115">Запуск выполнения команды SQL: %1</span><span class="sxs-lookup"><span data-stu-id="11c90-115">Starting SQL command execution: %1</span></span>  
  
## <a name="details"></a><span data-ttu-id="11c90-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="11c90-116">Details</span></span>  
  
|<span data-ttu-id="11c90-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="11c90-117">Data Item Name</span></span>|<span data-ttu-id="11c90-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="11c90-118">Data Item Type</span></span>|<span data-ttu-id="11c90-119">Описание</span><span class="sxs-lookup"><span data-stu-id="11c90-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="11c90-120">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="11c90-120">SqlCommand</span></span>|<span data-ttu-id="11c90-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="11c90-121">xs:string</span></span>|<span data-ttu-id="11c90-122">Команда SQL, которая была выполнена.</span><span class="sxs-lookup"><span data-stu-id="11c90-122">The SQL command that was executed.</span></span>|  
|<span data-ttu-id="11c90-123">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="11c90-123">AppDomain</span></span>|<span data-ttu-id="11c90-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="11c90-124">xs:string</span></span>|<span data-ttu-id="11c90-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="11c90-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
