---
ms.openlocfilehash: cf1a8169351e29c18d85303fb32d4394877448f4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235964"
---
### <a name="log-file-name-created-by-the-objectcontextcreatedatabase-method-has-changed-to-match-sql-server-specifications"></a><span data-ttu-id="675ba-101">Имя файла журнала, созданного методом ObjectContext.CreateDatabase, изменилось в соответствии со спецификациями SQL Server</span><span class="sxs-lookup"><span data-stu-id="675ba-101">Log file name created by the ObjectContext.CreateDatabase method has changed to match SQL Server specifications</span></span>

|   |   |
|---|---|
|<span data-ttu-id="675ba-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="675ba-102">Details</span></span>|<span data-ttu-id="675ba-103">При вызове метода <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=name> либо напрямую, либо с использованием Code First с поставщиком SqlClient и значения AttachDBFilename в строке подключения он создает файл журнала с именем filename_log.ldf вместо filename.ldf (где filename — имя файла, заданное значением AttachDBFilename).</span><span class="sxs-lookup"><span data-stu-id="675ba-103">When the <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=name> method is called either directly or by using Code First with the SqlClient provider and an AttachDBFilename value in the connection string, it creates a log file named filename_log.ldf instead of filename.ldf (where filename is the name of the file specified by the AttachDBFilename value).</span></span> <span data-ttu-id="675ba-104">Это изменение улучшает отладку, предоставляя файл журнала, имя которого соответствует спецификациям SQL Server.</span><span class="sxs-lookup"><span data-stu-id="675ba-104">This change improves debugging by providing a log file named according to SQL Server specifications.</span></span>|
|<span data-ttu-id="675ba-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="675ba-105">Suggestion</span></span>|<span data-ttu-id="675ba-106">Если имя файла журнала важно для приложения, приложение следует обновить для использования стандартного формата имени файла _log.ldf.</span><span class="sxs-lookup"><span data-stu-id="675ba-106">If the log file name is important for an app, the app should be updated to expect the standard _log.ldf file name format.</span></span>|
|<span data-ttu-id="675ba-107">Область</span><span class="sxs-lookup"><span data-stu-id="675ba-107">Scope</span></span>|<span data-ttu-id="675ba-108">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="675ba-108">Edge</span></span>|
|<span data-ttu-id="675ba-109">Версия</span><span class="sxs-lookup"><span data-stu-id="675ba-109">Version</span></span>|<span data-ttu-id="675ba-110">4.5</span><span class="sxs-lookup"><span data-stu-id="675ba-110">4.5</span></span>|
|<span data-ttu-id="675ba-111">Тип</span><span class="sxs-lookup"><span data-stu-id="675ba-111">Type</span></span>|<span data-ttu-id="675ba-112">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="675ba-112">Runtime</span></span>|
|<span data-ttu-id="675ba-113">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="675ba-113">Affected APIs</span></span>|<ul><li><xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType></li></ul>|
