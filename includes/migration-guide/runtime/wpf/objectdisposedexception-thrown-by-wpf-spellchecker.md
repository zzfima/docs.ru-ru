---
ms.openlocfilehash: 9d09f598538b9d5ee3f995d6281b8eb4b2668050
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802560"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a><span data-ttu-id="ebe13-101">Исключение ObjectDisposedException, создаваемое средством проверки орфографии WPF</span><span class="sxs-lookup"><span data-stu-id="ebe13-101">ObjectDisposedException thrown by WPF spellchecker</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ebe13-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="ebe13-102">Details</span></span>|<span data-ttu-id="ebe13-103">В некоторых случаях при завершении работы приложений WPF происходит сбой с исключением <xref:System.ObjectDisposedException?displayProperty=name>, создаваемым средством проверки орфографии.</span><span class="sxs-lookup"><span data-stu-id="ebe13-103">WPF applications occasionally crash during application shutdown with an <xref:System.ObjectDisposedException?displayProperty=name> thrown by the spellchecker.</span></span> <span data-ttu-id="ebe13-104">Эта ошибка исправлена в WPF .NET Framework 4.7 за счет правильной обработки этого исключения, что позволяет исключить подобное нежелательное поведение приложений.</span><span class="sxs-lookup"><span data-stu-id="ebe13-104">This is fixed in .NET Framework 4.7 WPF by handling the exception gracefully, and thus ensuring that applications are no longer adversely affected.</span></span> <span data-ttu-id="ebe13-105">Следует отметить, что случайные первичные исключения могут по-прежнему наблюдаться в приложениях, выполняемых в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="ebe13-105">It should be noted that occasional first-chance exceptions would continue to be observed in applications running under a debugger.</span></span>|
|<span data-ttu-id="ebe13-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="ebe13-106">Suggestion</span></span>|<span data-ttu-id="ebe13-107">Выполните обновление до .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="ebe13-107">Upgrade to .NET Framework 4.7</span></span>|
|<span data-ttu-id="ebe13-108">Область</span><span class="sxs-lookup"><span data-stu-id="ebe13-108">Scope</span></span>|<span data-ttu-id="ebe13-109">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="ebe13-109">Edge</span></span>|
|<span data-ttu-id="ebe13-110">Версия</span><span class="sxs-lookup"><span data-stu-id="ebe13-110">Version</span></span>|<span data-ttu-id="ebe13-111">4.6.1</span><span class="sxs-lookup"><span data-stu-id="ebe13-111">4.6.1</span></span>|
|<span data-ttu-id="ebe13-112">Тип</span><span class="sxs-lookup"><span data-stu-id="ebe13-112">Type</span></span>|<span data-ttu-id="ebe13-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="ebe13-113">Runtime</span></span>|

