---
ms.openlocfilehash: 946096cb9510ca12bbd2cecd00099142308b072a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804868"
---
### <a name="keytips-behavior-improved-in-wpf"></a><span data-ttu-id="7cb21-101">Улучшенные подсказки клавиш в WPF</span><span class="sxs-lookup"><span data-stu-id="7cb21-101">Keytips behavior improved in WPF</span></span>

|   |   |
|---|---|
|<span data-ttu-id="7cb21-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="7cb21-102">Details</span></span>|<span data-ttu-id="7cb21-103">Поведение подсказок клавиш было изменено и теперь совпадает с поведением в проводнике и Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="7cb21-103">Keytips behavior has been modified to bring parity with behavior on Microsoft Word and Windows Explorer.</span></span> <span data-ttu-id="7cb21-104">WPF проверяет, включено ли состояние подсказки клавиш в случае, если нажата <xref:System.Windows.Input.KeyEventArgs.SystemKey> (в частности, <xref:System.Windows.Input.Key> или <xref:System.Windows.Input.Key.F11>), и обрабатывает клавиши подсказок соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="7cb21-104">By checking whether keytip state is enabled or not in the case of a <xref:System.Windows.Input.KeyEventArgs.SystemKey> (in particular, <xref:System.Windows.Input.Key> or <xref:System.Windows.Input.Key.F11>) being pressed, WPF handles keytip keys appropriately.</span></span> <span data-ttu-id="7cb21-105">Подсказки клавиш теперь закрывают меню, даже если оно открыто с помощью мыши.</span><span class="sxs-lookup"><span data-stu-id="7cb21-105">Keytips now dismiss a menu even when it is opened by mouse.</span></span>|
|<span data-ttu-id="7cb21-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="7cb21-106">Suggestion</span></span>|<span data-ttu-id="7cb21-107">Н/Д</span><span class="sxs-lookup"><span data-stu-id="7cb21-107">N/A</span></span>|
|<span data-ttu-id="7cb21-108">Область</span><span class="sxs-lookup"><span data-stu-id="7cb21-108">Scope</span></span>|<span data-ttu-id="7cb21-109">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="7cb21-109">Edge</span></span>|
|<span data-ttu-id="7cb21-110">Версия</span><span class="sxs-lookup"><span data-stu-id="7cb21-110">Version</span></span>|<span data-ttu-id="7cb21-111">4.7.2</span><span class="sxs-lookup"><span data-stu-id="7cb21-111">4.7.2</span></span>|
|<span data-ttu-id="7cb21-112">Тип</span><span class="sxs-lookup"><span data-stu-id="7cb21-112">Type</span></span>|<span data-ttu-id="7cb21-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="7cb21-113">Runtime</span></span>|
