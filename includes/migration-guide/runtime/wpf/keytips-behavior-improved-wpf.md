---
ms.openlocfilehash: 946096cb9510ca12bbd2cecd00099142308b072a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236155"
---
### <a name="keytips-behavior-improved-in-wpf"></a><span data-ttu-id="6fdfa-101">Улучшенные подсказки клавиш в WPF</span><span class="sxs-lookup"><span data-stu-id="6fdfa-101">Keytips behavior improved in WPF</span></span>

|   |   |
|---|---|
|<span data-ttu-id="6fdfa-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="6fdfa-102">Details</span></span>|<span data-ttu-id="6fdfa-103">Поведение подсказок клавиш было изменено и теперь совпадает с поведением в проводнике и Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="6fdfa-103">Keytips behavior has been modified to bring parity with behavior on Microsoft Word and Windows Explorer.</span></span> <span data-ttu-id="6fdfa-104">WPF проверяет, включено ли состояние подсказки клавиш в случае, если нажата <xref:System.Windows.Input.KeyEventArgs.SystemKey> (в частности, <xref:System.Windows.Input.Key> или <xref:System.Windows.Input.Key.F11>), и обрабатывает клавиши подсказок соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="6fdfa-104">By checking whether keytip state is enabled or not in the case of a <xref:System.Windows.Input.KeyEventArgs.SystemKey> (in particular, <xref:System.Windows.Input.Key> or <xref:System.Windows.Input.Key.F11>) being pressed, WPF handles keytip keys appropriately.</span></span> <span data-ttu-id="6fdfa-105">Подсказки клавиш теперь закрывают меню, даже если оно открыто с помощью мыши.</span><span class="sxs-lookup"><span data-stu-id="6fdfa-105">Keytips now dismiss a menu even when it is opened by mouse.</span></span>|
|<span data-ttu-id="6fdfa-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="6fdfa-106">Suggestion</span></span>|<span data-ttu-id="6fdfa-107">Н/Д</span><span class="sxs-lookup"><span data-stu-id="6fdfa-107">N/A</span></span>|
|<span data-ttu-id="6fdfa-108">Область</span><span class="sxs-lookup"><span data-stu-id="6fdfa-108">Scope</span></span>|<span data-ttu-id="6fdfa-109">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="6fdfa-109">Edge</span></span>|
|<span data-ttu-id="6fdfa-110">Версия</span><span class="sxs-lookup"><span data-stu-id="6fdfa-110">Version</span></span>|<span data-ttu-id="6fdfa-111">4.7.2</span><span class="sxs-lookup"><span data-stu-id="6fdfa-111">4.7.2</span></span>|
|<span data-ttu-id="6fdfa-112">Тип</span><span class="sxs-lookup"><span data-stu-id="6fdfa-112">Type</span></span>|<span data-ttu-id="6fdfa-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="6fdfa-113">Runtime</span></span>|
