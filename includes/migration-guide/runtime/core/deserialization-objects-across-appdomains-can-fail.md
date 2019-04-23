---
ms.openlocfilehash: 891c29b731214fb0028e960256b79cfc267d86b9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235461"
---
### <a name="deserialization-of-objects-across-appdomains-can-fail"></a><span data-ttu-id="4e2db-101">Десериализация объектов между доменами приложений может завершиться сбоем</span><span class="sxs-lookup"><span data-stu-id="4e2db-101">Deserialization of objects across appdomains can fail</span></span>

|   |   |
|---|---|
|<span data-ttu-id="4e2db-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="4e2db-102">Details</span></span>|<span data-ttu-id="4e2db-103">В некоторых случаях, когда приложение использует два или большее количество доменов с разными базовыми папками приложения, при попытке выполнить десериализацию объектов в логическом контексте вызова между доменами приложения возникнет исключение.</span><span class="sxs-lookup"><span data-stu-id="4e2db-103">In some cases, when an app uses two or more app domains with different application bases, trying to deserialize objects in the logical call context across app domains throws an exception.</span></span>|
|<span data-ttu-id="4e2db-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="4e2db-104">Suggestion</span></span>|<span data-ttu-id="4e2db-105">См. статью [Устранение рисков: десериализация объектов между доменами приложений](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)</span><span class="sxs-lookup"><span data-stu-id="4e2db-105">See [Mitigation: Deserialization of Objects Across App Domains](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)</span></span>|
|<span data-ttu-id="4e2db-106">Область</span><span class="sxs-lookup"><span data-stu-id="4e2db-106">Scope</span></span>|<span data-ttu-id="4e2db-107">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="4e2db-107">Edge</span></span>|
|<span data-ttu-id="4e2db-108">Версия</span><span class="sxs-lookup"><span data-stu-id="4e2db-108">Version</span></span>|<span data-ttu-id="4e2db-109">4.5.1</span><span class="sxs-lookup"><span data-stu-id="4e2db-109">4.5.1</span></span>|
|<span data-ttu-id="4e2db-110">Тип</span><span class="sxs-lookup"><span data-stu-id="4e2db-110">Type</span></span>|<span data-ttu-id="4e2db-111">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="4e2db-111">Runtime</span></span>|
