---
ms.openlocfilehash: a3f5f512fd17ab2b076f868be24e5c73d8698c49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802560"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a><span data-ttu-id="b47fe-101">Исключение ObjectDisposedException, создаваемое средством проверки орфографии WPF</span><span class="sxs-lookup"><span data-stu-id="b47fe-101">ObjectDisposedException thrown by WPF spellchecker</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b47fe-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="b47fe-102">Details</span></span>|<span data-ttu-id="b47fe-103">В некоторых случаях при завершении работы приложений WPF происходит сбой с исключением <xref:System.ObjectDisposedException?displayProperty=name>, создаваемым средством проверки орфографии.</span><span class="sxs-lookup"><span data-stu-id="b47fe-103">WPF applications occasionally crash during application shutdown with an <xref:System.ObjectDisposedException?displayProperty=name> thrown by the spellchecker.</span></span> <span data-ttu-id="b47fe-104">Эта ошибка исправлена в WPF .NET Framework 4.7 за счет правильной обработки этого исключения, что позволяет исключить подобное нежелательное поведение приложений.</span><span class="sxs-lookup"><span data-stu-id="b47fe-104">This is fixed in .NET Framework 4.7 WPF by handling the exception gracefully, and thus ensuring that applications are no longer adversely affected.</span></span> <span data-ttu-id="b47fe-105">Следует отметить, что случайные первичные исключения могут по-прежнему наблюдаться в приложениях, выполняемых в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="b47fe-105">It should be noted that occasional first-chance exceptions would continue to be observed in applications running under a debugger.</span></span>|
|<span data-ttu-id="b47fe-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="b47fe-106">Suggestion</span></span>|<span data-ttu-id="b47fe-107">Выполните обновление до .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="b47fe-107">Upgrade to .NET Framework 4.7</span></span>|
|<span data-ttu-id="b47fe-108">Область</span><span class="sxs-lookup"><span data-stu-id="b47fe-108">Scope</span></span>|<span data-ttu-id="b47fe-109">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="b47fe-109">Edge</span></span>|
|<span data-ttu-id="b47fe-110">Version</span><span class="sxs-lookup"><span data-stu-id="b47fe-110">Version</span></span>|<span data-ttu-id="b47fe-111">4.6.1</span><span class="sxs-lookup"><span data-stu-id="b47fe-111">4.6.1</span></span>|
|<span data-ttu-id="b47fe-112">Type</span><span class="sxs-lookup"><span data-stu-id="b47fe-112">Type</span></span>|<span data-ttu-id="b47fe-113">Параметры выполнения</span><span class="sxs-lookup"><span data-stu-id="b47fe-113">Runtime</span></span>|
