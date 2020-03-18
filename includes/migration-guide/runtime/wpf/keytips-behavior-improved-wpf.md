---
ms.openlocfilehash: 946096cb9510ca12bbd2cecd00099142308b072a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67856959"
---
### <a name="keytips-behavior-improved-in-wpf"></a><span data-ttu-id="e9d4d-101">Улучшенные подсказки клавиш в WPF</span><span class="sxs-lookup"><span data-stu-id="e9d4d-101">Keytips behavior improved in WPF</span></span>

|   |   |
|---|---|
|<span data-ttu-id="e9d4d-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="e9d4d-102">Details</span></span>|<span data-ttu-id="e9d4d-103">Поведение подсказок клавиш было изменено и теперь совпадает с поведением в проводнике и Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="e9d4d-103">Keytips behavior has been modified to bring parity with behavior on Microsoft Word and Windows Explorer.</span></span> <span data-ttu-id="e9d4d-104">WPF проверяет, включено ли состояние подсказки клавиш в случае, если нажата <xref:System.Windows.Input.KeyEventArgs.SystemKey> (в частности, <xref:System.Windows.Input.Key> или <xref:System.Windows.Input.Key.F11>), и обрабатывает клавиши подсказок соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="e9d4d-104">By checking whether keytip state is enabled or not in the case of a <xref:System.Windows.Input.KeyEventArgs.SystemKey> (in particular, <xref:System.Windows.Input.Key> or <xref:System.Windows.Input.Key.F11>) being pressed, WPF handles keytip keys appropriately.</span></span> <span data-ttu-id="e9d4d-105">Подсказки клавиш теперь закрывают меню, даже если оно открыто с помощью мыши.</span><span class="sxs-lookup"><span data-stu-id="e9d4d-105">Keytips now dismiss a menu even when it is opened by mouse.</span></span>|
|<span data-ttu-id="e9d4d-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="e9d4d-106">Suggestion</span></span>|<span data-ttu-id="e9d4d-107">Недоступно</span><span class="sxs-lookup"><span data-stu-id="e9d4d-107">N/A</span></span>|
|<span data-ttu-id="e9d4d-108">Область</span><span class="sxs-lookup"><span data-stu-id="e9d4d-108">Scope</span></span>|<span data-ttu-id="e9d4d-109">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="e9d4d-109">Edge</span></span>|
|<span data-ttu-id="e9d4d-110">Version</span><span class="sxs-lookup"><span data-stu-id="e9d4d-110">Version</span></span>|<span data-ttu-id="e9d4d-111">4.7.2</span><span class="sxs-lookup"><span data-stu-id="e9d4d-111">4.7.2</span></span>|
|<span data-ttu-id="e9d4d-112">Type</span><span class="sxs-lookup"><span data-stu-id="e9d4d-112">Type</span></span>|<span data-ttu-id="e9d4d-113">Параметры выполнения</span><span class="sxs-lookup"><span data-stu-id="e9d4d-113">Runtime</span></span>|
