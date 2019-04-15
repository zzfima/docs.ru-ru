---
ms.openlocfilehash: 4cc91e7c6054fdb8e96cecf7120df5b9f25de56c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235578"
---
### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a><span data-ttu-id="980b9-101">Каталоги MEF реализуют IEnumerable и поэтому больше не могут использоваться для создания сериализатора</span><span class="sxs-lookup"><span data-stu-id="980b9-101">MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer</span></span>

|   |   |
|---|---|
|<span data-ttu-id="980b9-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="980b9-102">Details</span></span>|<span data-ttu-id="980b9-103">Начиная с .NET Framework 4.5 каталоги MEF реализуют IEnumerable и поэтому больше не могут использоваться для создания сериализатора (объекта <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name>).</span><span class="sxs-lookup"><span data-stu-id="980b9-103">Starting with the .NET Framework 4.5, MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer (<xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> object).</span></span> <span data-ttu-id="980b9-104">При попытке сериализации каталога MEF происходит вызов исключения.</span><span class="sxs-lookup"><span data-stu-id="980b9-104">Trying to serialize a MEF catalog throws an exception.</span></span>|
|<span data-ttu-id="980b9-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="980b9-105">Suggestion</span></span>|<span data-ttu-id="980b9-106">Больше не следует использовать MEF для создания сериализатора.</span><span class="sxs-lookup"><span data-stu-id="980b9-106">Can no longer use MEF to create a serializer</span></span>|
|<span data-ttu-id="980b9-107">Область</span><span class="sxs-lookup"><span data-stu-id="980b9-107">Scope</span></span>|<span data-ttu-id="980b9-108">Значительно</span><span class="sxs-lookup"><span data-stu-id="980b9-108">Major</span></span>|
|<span data-ttu-id="980b9-109">Версия</span><span class="sxs-lookup"><span data-stu-id="980b9-109">Version</span></span>|<span data-ttu-id="980b9-110">4.5</span><span class="sxs-lookup"><span data-stu-id="980b9-110">4.5</span></span>|
|<span data-ttu-id="980b9-111">Тип</span><span class="sxs-lookup"><span data-stu-id="980b9-111">Type</span></span>|<span data-ttu-id="980b9-112">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="980b9-112">Runtime</span></span>|
