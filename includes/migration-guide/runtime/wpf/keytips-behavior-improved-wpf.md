---
ms.openlocfilehash: d7cf32eb369e2607ee540d7188cc680b9506c261
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760759"
---
### <a name="keytips-behavior-improved-in-wpf"></a><span data-ttu-id="95a52-101">Улучшенные подсказки клавиш в WPF</span><span class="sxs-lookup"><span data-stu-id="95a52-101">Keytips behavior improved in WPF</span></span>

|   |   |
|---|---|
|<span data-ttu-id="95a52-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="95a52-102">Details</span></span>|<span data-ttu-id="95a52-103">Поведение подсказок клавиш было изменено и теперь совпадает с поведением в проводнике и Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="95a52-103">Keytips behavior has been modified to bring parity with behavior on Microsoft Word and Windows Explorer.</span></span> <span data-ttu-id="95a52-104">WPF проверяет, включено ли состояние подсказки клавиш в случае, если нажата <xref:System.Windows.Input.KeyEventArgs.SystemKey> (в частности, <xref:System.Windows.Input.Key> или <xref:System.Windows.Input.Key.F11>), и обрабатывает клавиши подсказок соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="95a52-104">By checking whether keytip state is enabled or not in the case of a <xref:System.Windows.Input.KeyEventArgs.SystemKey> (in particular, <xref:System.Windows.Input.Key> or <xref:System.Windows.Input.Key.F11>) being pressed, WPF handles keytip keys appropriately.</span></span> <span data-ttu-id="95a52-105">Подсказки клавиш теперь закрывают меню, даже если оно открыто с помощью мыши.</span><span class="sxs-lookup"><span data-stu-id="95a52-105">Keytips now dismiss a menu even when it is opened by mouse.</span></span>|
|<span data-ttu-id="95a52-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="95a52-106">Suggestion</span></span>|<span data-ttu-id="95a52-107">Н/Д</span><span class="sxs-lookup"><span data-stu-id="95a52-107">N/A</span></span>|
|<span data-ttu-id="95a52-108">Область</span><span class="sxs-lookup"><span data-stu-id="95a52-108">Scope</span></span>|<span data-ttu-id="95a52-109">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="95a52-109">Edge</span></span>|
|<span data-ttu-id="95a52-110">Версия</span><span class="sxs-lookup"><span data-stu-id="95a52-110">Version</span></span>|<span data-ttu-id="95a52-111">4.7.2</span><span class="sxs-lookup"><span data-stu-id="95a52-111">4.7.2</span></span>|
|<span data-ttu-id="95a52-112">Тип</span><span class="sxs-lookup"><span data-stu-id="95a52-112">Type</span></span>|<span data-ttu-id="95a52-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="95a52-113">Runtime</span></span>|

