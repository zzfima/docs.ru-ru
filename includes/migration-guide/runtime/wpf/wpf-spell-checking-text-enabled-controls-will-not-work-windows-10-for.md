---
ms.openlocfilehash: abb89099c4c8a5d9c0e55ef8f357faf44e75b045
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858508"
---
### <a name="wpf-spell-checking-in-text-enabled-controls-will-not-work-in-windows-10-for-languages-not-in-the-oss-input-language-list"></a><span data-ttu-id="ae528-101">Проверка орфографии WPF в элементах управления с поддержкой текста не будет работать в Windows 10 для языков, не указанных в списке языков ввода ОС</span><span class="sxs-lookup"><span data-stu-id="ae528-101">WPF spell checking in text-enabled controls will not work in Windows 10 for languages not in the OS's input language list</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ae528-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="ae528-102">Details</span></span>|<span data-ttu-id="ae528-103">В Windows 10 средство проверки орфографии может не работать для элементов управления WPF с поддержкой текста, поскольку возможности проверки орфографии платформы доступны только для языков из списка языков ввода. В Windows 10 при добавлении языка в список доступных клавиатур Windows автоматически загружает и устанавливает соответствующий пакет компонента по запросу (FOD), который предоставляет возможности проверки орфографии.</span><span class="sxs-lookup"><span data-stu-id="ae528-103">When running on Windows 10, the spell checker may not work for WPF text-enabled controls because platform spell-checking capabilities are available only for languages present in the input languages list.In Windows 10, when a language is added to the list of available keyboards, Windows automatically downloads and installs a corresponding Feature on Demand (FOD) package that provides spell-checking capabilities.</span></span> <span data-ttu-id="ae528-104">При добавлении языка в список языков ввода проверка орфографии будет поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="ae528-104">By adding the language to the input languages list, the spell checker will be supported.</span></span>|
|<span data-ttu-id="ae528-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="ae528-105">Suggestion</span></span>|<span data-ttu-id="ae528-106">Имейте в виду, что язык или текст, проверка которого выполняется, следует добавить как язык ввода, чтобы функция проверки орфографии работала в Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ae528-106">Be aware that the language or text to be spell-checked must be added as an input language for spell-checking to work in Windows 10.</span></span>|
|<span data-ttu-id="ae528-107">Область</span><span class="sxs-lookup"><span data-stu-id="ae528-107">Scope</span></span>|<span data-ttu-id="ae528-108">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="ae528-108">Edge</span></span>|
|<span data-ttu-id="ae528-109">Version</span><span class="sxs-lookup"><span data-stu-id="ae528-109">Version</span></span>|<span data-ttu-id="ae528-110">4.6</span><span class="sxs-lookup"><span data-stu-id="ae528-110">4.6</span></span>|
|<span data-ttu-id="ae528-111">Type</span><span class="sxs-lookup"><span data-stu-id="ae528-111">Type</span></span>|<span data-ttu-id="ae528-112">Параметры выполнения</span><span class="sxs-lookup"><span data-stu-id="ae528-112">Runtime</span></span>|
