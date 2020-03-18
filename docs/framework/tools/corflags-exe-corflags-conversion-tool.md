---
title: CorFlags.exe (средство преобразования CorFlags)
ms.date: 03/30/2017
helpviewer_keywords:
- CorFlags conversion tool
- CorFlags.exe
- portable executable files, CorFlags section
ms.assetid: ef900f8f-71ca-4dde-9b8c-95ddb0d7d89c
ms.openlocfilehash: e1251b6660db45f3af4f6e57114b1b10da18bd0a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73129864"
---
# <a name="corflagsexe-corflags-conversion-tool"></a><span data-ttu-id="dbbdf-102">CorFlags.exe (средство преобразования CorFlags)</span><span class="sxs-lookup"><span data-stu-id="dbbdf-102">CorFlags.exe (CorFlags Conversion Tool)</span></span>
<span data-ttu-id="dbbdf-103">Средство преобразования CorFlags позволяет настраивать раздел CorFlags в заголовке переносимого исполняемого образа.</span><span class="sxs-lookup"><span data-stu-id="dbbdf-103">The CorFlags Conversion tool allows you to configure the CorFlags section of the header of a portable executable image.</span></span>  
  
 <span data-ttu-id="dbbdf-104">Это средство автоматически устанавливается с Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dbbdf-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="dbbdf-105">Чтобы применить этот инструмент, воспользуйтесь командной строкой разработчика для Visual Studio (или командной строкой Visual Studio в Windows 7).</span><span class="sxs-lookup"><span data-stu-id="dbbdf-105">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="dbbdf-106">Дополнительные сведения см. в разделе [Командные строки](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="dbbdf-106">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="dbbdf-107">В командной строке введите следующее.</span><span class="sxs-lookup"><span data-stu-id="dbbdf-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbbdf-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dbbdf-108">Syntax</span></span>  
  
```console  
CorFlags.exe assembly [options]  
```  
  
## <a name="parameters"></a><span data-ttu-id="dbbdf-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="dbbdf-109">Parameters</span></span>  
  
|<span data-ttu-id="dbbdf-110">Обязательный параметр</span><span class="sxs-lookup"><span data-stu-id="dbbdf-110">Required parameter</span></span>|<span data-ttu-id="dbbdf-111">Описание:</span><span class="sxs-lookup"><span data-stu-id="dbbdf-111">Description</span></span>|  
|------------------------|-----------------|  
|`assembly`|<span data-ttu-id="dbbdf-112">Имя сборки, для которой требуется настроить раздел CorFlags.</span><span class="sxs-lookup"><span data-stu-id="dbbdf-112">The name of the assembly for which to configure the CorFlags.</span></span>|  
  
|<span data-ttu-id="dbbdf-113">Параметр</span><span class="sxs-lookup"><span data-stu-id="dbbdf-113">Option</span></span>|<span data-ttu-id="dbbdf-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="dbbdf-114">Description</span></span>|  
|:------------|-----------------|  
|`-32BIT[REQ]+`|<span data-ttu-id="dbbdf-115">Устанавливает флаг 32BITREQUIRED.</span><span class="sxs-lookup"><span data-stu-id="dbbdf-115">Sets the 32BITREQUIRED flag.</span></span>|  
|`-32BIT[REQ]-`|<span data-ttu-id="dbbdf-116">Снимает флаг 32BITREQUIRED.</span><span class="sxs-lookup"><span data-stu-id="dbbdf-116">Clears the 32BITREQUIRED flag.</span></span>|  
|`-32BITPREF+`|<span data-ttu-id="dbbdf-117">Устанавливает флаг 32BITPREFERRED.</span><span class="sxs-lookup"><span data-stu-id="dbbdf-117">Sets the 32BITPREFERRED flag.</span></span> <span data-ttu-id="dbbdf-118">Приложение выполняется как 32-разрядный процесс даже на 64-разрядных платформах.</span><span class="sxs-lookup"><span data-stu-id="dbbdf-118">The app runs as a 32-bit process even on 64-bit platforms.</span></span> <span data-ttu-id="dbbdf-119">Устанавливайте этот флаг только в EXE-файлах.</span><span class="sxs-lookup"><span data-stu-id="dbbdf-119">Set this flag only on EXE files.</span></span> <span data-ttu-id="dbbdf-120">Если флаг установлен для библиотеки DLL, она не загружается в 64-разрядных процессах и создается исключение <xref:System.BadImageFormatException>.</span><span class="sxs-lookup"><span data-stu-id="dbbdf-120">If the flag is set on a DLL, the DLL fails to load in 64-bit processes, and a <xref:System.BadImageFormatException> exception is thrown.</span></span> <span data-ttu-id="dbbdf-121">Файл EXE с этим флагом можно загрузить в 64-разрядный процесс.</span><span class="sxs-lookup"><span data-stu-id="dbbdf-121">An EXE file with this flag can be loaded into a 64-bit process.</span></span><br /><br /> <span data-ttu-id="dbbdf-122">Новые возможности .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="dbbdf-122">New in the .NET Framework 4.5.</span></span>|  
|`-32BITPREF-`|<span data-ttu-id="dbbdf-123">Снимает флаг 32BITPREFERRED.</span><span class="sxs-lookup"><span data-stu-id="dbbdf-123">Clears the 32BITPREFERRED flag.</span></span><br /><br /> <span data-ttu-id="dbbdf-124">Новые возможности .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="dbbdf-124">New in the .NET Framework 4.5.</span></span>|  
|`-?`|<span data-ttu-id="dbbdf-125">Отображает синтаксис команд и параметров программы.</span><span class="sxs-lookup"><span data-stu-id="dbbdf-125">Displays command syntax and options for the tool.</span></span>|  
|`-Force`|<span data-ttu-id="dbbdf-126">Выполняет принудительное обновление, даже если сборка имеет строгое имя.</span><span class="sxs-lookup"><span data-stu-id="dbbdf-126">Forces an update even if the assembly is strong-named.</span></span> <span data-ttu-id="dbbdf-127">**Важно!** При обновлении сборки со строгим именем перед выполнением ее кода необходимо снова подписать сборку.</span><span class="sxs-lookup"><span data-stu-id="dbbdf-127">**Important:**  If you update a strong-named assembly, you must sign it again before executing its code.</span></span>|  
|`-help`|<span data-ttu-id="dbbdf-128">Отображает синтаксис команд и параметров программы.</span><span class="sxs-lookup"><span data-stu-id="dbbdf-128">Displays command syntax and options for the tool.</span></span>|  
|`-ILONLY+`|<span data-ttu-id="dbbdf-129">Устанавливает флаг ILONLY.</span><span class="sxs-lookup"><span data-stu-id="dbbdf-129">Sets the ILONLY flag.</span></span>|  
|`-ILONLY-`|<span data-ttu-id="dbbdf-130">Снимает флаг ILONLY.</span><span class="sxs-lookup"><span data-stu-id="dbbdf-130">Clears the ILONLY flag.</span></span>|  
|`-nologo`|<span data-ttu-id="dbbdf-131">Отключает отображение эмблемы Майкрософт при запуске.</span><span class="sxs-lookup"><span data-stu-id="dbbdf-131">Suppresses the Microsoft startup banner display.</span></span>|  
|`-RevertCLRHeader`|<span data-ttu-id="dbbdf-132">Задает версии заголовка CLR значение 2.0.</span><span class="sxs-lookup"><span data-stu-id="dbbdf-132">Reverts the CLR header version to 2.0.</span></span>|  
|`-UpgradeCLRHeader`|<span data-ttu-id="dbbdf-133">Обновляет версию заголовка CLR до версии 2.5.</span><span class="sxs-lookup"><span data-stu-id="dbbdf-133">Upgrades the CLR header version to 2.5.</span></span> <span data-ttu-id="dbbdf-134">**Примечание.** Для оптимального выполнения сборок они должны иметь версию заголовка CLR 2.5 или выше.</span><span class="sxs-lookup"><span data-stu-id="dbbdf-134">**Note:**  Assemblies must have a CLR header version of 2.5 or greater to run natively.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dbbdf-135">Remarks</span><span class="sxs-lookup"><span data-stu-id="dbbdf-135">Remarks</span></span>  
 <span data-ttu-id="dbbdf-136">Если другие параметры не заданы, средство преобразования CorFlags отображает флаги заданной сборки.</span><span class="sxs-lookup"><span data-stu-id="dbbdf-136">If no options are specified, the CorFlags Conversion tool displays the flags for the specified assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbbdf-137">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="dbbdf-137">See also</span></span>

- [<span data-ttu-id="dbbdf-138">Инструменты</span><span class="sxs-lookup"><span data-stu-id="dbbdf-138">Tools</span></span>](index.md)
- [<span data-ttu-id="dbbdf-139">64-разрядные приложения</span><span class="sxs-lookup"><span data-stu-id="dbbdf-139">64-bit Applications</span></span>](../64-bit-apps.md)
- [<span data-ttu-id="dbbdf-140">Командные строки</span><span class="sxs-lookup"><span data-stu-id="dbbdf-140">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
