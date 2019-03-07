---
title: 1004 ― WorkflowInstanceAborted
ms.date: 03/30/2017
ms.assetid: edb9ab8c-0b9a-488d-aa96-9c8c7984b53c
ms.openlocfilehash: d34f6f1ab6af8e06a0f28fb043faf9fe16a8b211
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485191"
---
# <a name="1004---workflowinstanceaborted"></a><span data-ttu-id="a4a69-102">1004 ― WorkflowInstanceAborted</span><span class="sxs-lookup"><span data-stu-id="a4a69-102">1004 - WorkflowInstanceAborted</span></span>

## <a name="properties"></a><span data-ttu-id="a4a69-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="a4a69-103">Properties</span></span>

|||
|-|-|
|<span data-ttu-id="a4a69-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="a4a69-104">ID</span></span>|<span data-ttu-id="a4a69-105">1004</span><span class="sxs-lookup"><span data-stu-id="a4a69-105">1004</span></span>|
|<span data-ttu-id="a4a69-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a4a69-106">Keywords</span></span>|<span data-ttu-id="a4a69-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a4a69-107">WFRuntime</span></span>|
|<span data-ttu-id="a4a69-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="a4a69-108">Level</span></span>|<span data-ttu-id="a4a69-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="a4a69-109">Information</span></span>|
|<span data-ttu-id="a4a69-110">Канал</span><span class="sxs-lookup"><span data-stu-id="a4a69-110">Channel</span></span>|<span data-ttu-id="a4a69-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="a4a69-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|

## <a name="description"></a><span data-ttu-id="a4a69-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="a4a69-112">Description</span></span>

<span data-ttu-id="a4a69-113">Указывает, что экземпляр рабочего процесса был прерван с исключением.</span><span class="sxs-lookup"><span data-stu-id="a4a69-113">Indicates a workflow instance has aborted with an exception.</span></span>

## <a name="message"></a><span data-ttu-id="a4a69-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="a4a69-114">Message</span></span>

<span data-ttu-id="a4a69-115">Выполнение элемента WorkflowInstance с идентификатором «%1» было прервано в результате исключения.</span><span class="sxs-lookup"><span data-stu-id="a4a69-115">WorkflowInstance Id: '%1' was aborted with an exception.</span></span>

## <a name="details"></a><span data-ttu-id="a4a69-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="a4a69-116">Details</span></span>

|<span data-ttu-id="a4a69-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="a4a69-117">Data Item Name</span></span>|<span data-ttu-id="a4a69-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="a4a69-118">Data Item Type</span></span>|<span data-ttu-id="a4a69-119">Описание</span><span class="sxs-lookup"><span data-stu-id="a4a69-119">Description</span></span>|
|--------------------|--------------------|-----------------|
|<span data-ttu-id="a4a69-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="a4a69-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="a4a69-121">Идентификатор экземпляра для рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="a4a69-121">The instance id for the workflow</span></span>|
|<span data-ttu-id="a4a69-122">Исключение</span><span class="sxs-lookup"><span data-stu-id="a4a69-122">Exception</span></span>|`xs:string`|<span data-ttu-id="a4a69-123">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="a4a69-123">The exception details for the exception</span></span>|
|<span data-ttu-id="a4a69-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a4a69-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a4a69-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a4a69-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
