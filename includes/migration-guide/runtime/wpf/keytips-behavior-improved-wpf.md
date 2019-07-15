---
ms.openlocfilehash: d7cf32eb369e2607ee540d7188cc680b9506c261
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67856959"
---
### <a name="keytips-behavior-improved-in-wpf"></a><span data-ttu-id="47db2-101">Улучшенные подсказки клавиш в WPF</span><span class="sxs-lookup"><span data-stu-id="47db2-101">Keytips behavior improved in WPF</span></span>

|   |   |
|---|---|
|<span data-ttu-id="47db2-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="47db2-102">Details</span></span>|<span data-ttu-id="47db2-103">Поведение подсказок клавиш было изменено и теперь совпадает с поведением в проводнике и Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="47db2-103">Keytips behavior has been modified to bring parity with behavior on Microsoft Word and Windows Explorer.</span></span> <span data-ttu-id="47db2-104">WPF проверяет, включено ли состояние подсказки клавиш в случае, если нажата <xref:System.Windows.Input.KeyEventArgs.SystemKey> (в частности, <xref:System.Windows.Input.Key> или <xref:System.Windows.Input.Key.F11>), и обрабатывает клавиши подсказок соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="47db2-104">By checking whether keytip state is enabled or not in the case of a <xref:System.Windows.Input.KeyEventArgs.SystemKey> (in particular, <xref:System.Windows.Input.Key> or <xref:System.Windows.Input.Key.F11>) being pressed, WPF handles keytip keys appropriately.</span></span> <span data-ttu-id="47db2-105">Подсказки клавиш теперь закрывают меню, даже если оно открыто с помощью мыши.</span><span class="sxs-lookup"><span data-stu-id="47db2-105">Keytips now dismiss a menu even when it is opened by mouse.</span></span>|
|<span data-ttu-id="47db2-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="47db2-106">Suggestion</span></span>|<span data-ttu-id="47db2-107">Н/Д</span><span class="sxs-lookup"><span data-stu-id="47db2-107">N/A</span></span>|
|<span data-ttu-id="47db2-108">Область</span><span class="sxs-lookup"><span data-stu-id="47db2-108">Scope</span></span>|<span data-ttu-id="47db2-109">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="47db2-109">Edge</span></span>|
|<span data-ttu-id="47db2-110">Версия</span><span class="sxs-lookup"><span data-stu-id="47db2-110">Version</span></span>|<span data-ttu-id="47db2-111">4.7.2</span><span class="sxs-lookup"><span data-stu-id="47db2-111">4.7.2</span></span>|
|<span data-ttu-id="47db2-112">Тип</span><span class="sxs-lookup"><span data-stu-id="47db2-112">Type</span></span>|<span data-ttu-id="47db2-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="47db2-113">Runtime</span></span>|

