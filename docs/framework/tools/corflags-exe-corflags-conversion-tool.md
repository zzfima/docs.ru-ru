---
title: "CorFlags.exe (средство преобразования CorFlags)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CorFlags conversion tool
- CorFlags.exe
- portable executable files, CorFlags section
ms.assetid: ef900f8f-71ca-4dde-9b8c-95ddb0d7d89c
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 111c697d4d62cd52cd7913039e3c17e8a25ab50d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corflagsexe-corflags-conversion-tool"></a><span data-ttu-id="a7e53-102">CorFlags.exe (средство преобразования CorFlags)</span><span class="sxs-lookup"><span data-stu-id="a7e53-102">CorFlags.exe (CorFlags Conversion Tool)</span></span>
<span data-ttu-id="a7e53-103">Средство преобразования CorFlags позволяет настраивать раздел CorFlags в заголовке переносимого исполняемого образа.</span><span class="sxs-lookup"><span data-stu-id="a7e53-103">The CorFlags Conversion tool allows you to configure the CorFlags section of the header of a portable executable image.</span></span>  
  
 <span data-ttu-id="a7e53-104">Эта программа автоматически устанавливается вместе с Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a7e53-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="a7e53-105">Чтобы применить этот инструмент, воспользуйтесь командной строкой разработчика (или командной строкой Visual Studio в Windows 7).</span><span class="sxs-lookup"><span data-stu-id="a7e53-105">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="a7e53-106">Дополнительные сведения см. в разделе [Командные строки](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="a7e53-106">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="a7e53-107">В командной строке введите следующее.</span><span class="sxs-lookup"><span data-stu-id="a7e53-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7e53-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a7e53-108">Syntax</span></span>  
  
```  
CorFlags.exe assembly [options]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a7e53-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="a7e53-109">Parameters</span></span>  
  
|<span data-ttu-id="a7e53-110">Обязательный параметр</span><span class="sxs-lookup"><span data-stu-id="a7e53-110">Required parameter</span></span>|<span data-ttu-id="a7e53-111">Описание:</span><span class="sxs-lookup"><span data-stu-id="a7e53-111">Description</span></span>|  
|------------------------|-----------------|  
|`assembly`|<span data-ttu-id="a7e53-112">Имя сборки, для которой требуется настроить раздел CorFlags.</span><span class="sxs-lookup"><span data-stu-id="a7e53-112">The name of the assembly for which to configure the CorFlags.</span></span>|  
  
|<span data-ttu-id="a7e53-113">Параметр</span><span class="sxs-lookup"><span data-stu-id="a7e53-113">Option</span></span>|<span data-ttu-id="a7e53-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="a7e53-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="a7e53-115">**/32BIT[REQ]+**</span><span class="sxs-lookup"><span data-stu-id="a7e53-115">**/32BIT[REQ]+**</span></span>|<span data-ttu-id="a7e53-116">Устанавливает флаг 32BITREQUIRED.</span><span class="sxs-lookup"><span data-stu-id="a7e53-116">Sets the 32BITREQUIRED flag.</span></span>|  
|<span data-ttu-id="a7e53-117">**/32BIT[REQ]-**</span><span class="sxs-lookup"><span data-stu-id="a7e53-117">**/32BIT[REQ]-**</span></span>|<span data-ttu-id="a7e53-118">Снимает флаг 32BITREQUIRED.</span><span class="sxs-lookup"><span data-stu-id="a7e53-118">Clears the 32BITREQUIRED flag.</span></span>|  
|<span data-ttu-id="a7e53-119">**/32BITPREF+**</span><span class="sxs-lookup"><span data-stu-id="a7e53-119">**/32BITPREF+**</span></span>|<span data-ttu-id="a7e53-120">Устанавливает флаг 32BITPREFERRED.</span><span class="sxs-lookup"><span data-stu-id="a7e53-120">Sets the 32BITPREFERRED flag.</span></span> <span data-ttu-id="a7e53-121">Приложение выполняется как 32-разрядный процесс даже на 64-разрядных платформах.</span><span class="sxs-lookup"><span data-stu-id="a7e53-121">The app runs as a 32-bit process even on 64-bit platforms.</span></span> <span data-ttu-id="a7e53-122">Устанавливайте этот флаг только в EXE-файлах.</span><span class="sxs-lookup"><span data-stu-id="a7e53-122">Set this flag only on EXE files.</span></span> <span data-ttu-id="a7e53-123">Если флаг установлен для библиотеки DLL, она не загружается в 64-разрядных процессах и создается исключение <xref:System.BadImageFormatException>.</span><span class="sxs-lookup"><span data-stu-id="a7e53-123">If the flag is set on a DLL, the DLL fails to load in 64-bit processes, and a <xref:System.BadImageFormatException> exception is thrown.</span></span> <span data-ttu-id="a7e53-124">Файл EXE с этим флагом можно загрузить в 64-разрядный процесс.</span><span class="sxs-lookup"><span data-stu-id="a7e53-124">An EXE file with this flag can be loaded into a 64-bit process.</span></span><br /><br /> <span data-ttu-id="a7e53-125">Новый параметр [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7e53-125">New in the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span>|  
|<span data-ttu-id="a7e53-126">**/32BITPREF-**</span><span class="sxs-lookup"><span data-stu-id="a7e53-126">**/32BITPREF-**</span></span>|<span data-ttu-id="a7e53-127">Снимает флаг 32BITPREFERRED.</span><span class="sxs-lookup"><span data-stu-id="a7e53-127">Clears the 32BITPREFERRED flag.</span></span><br /><br /> <span data-ttu-id="a7e53-128">Новый параметр [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7e53-128">New in the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span>|  
|<span data-ttu-id="a7e53-129">**/?**</span><span class="sxs-lookup"><span data-stu-id="a7e53-129">**/?**</span></span>|<span data-ttu-id="a7e53-130">Отображает синтаксис команд и параметров программы.</span><span class="sxs-lookup"><span data-stu-id="a7e53-130">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="a7e53-131">**/Force**</span><span class="sxs-lookup"><span data-stu-id="a7e53-131">**/Force**</span></span>|<span data-ttu-id="a7e53-132">Выполняет принудительное обновление, даже если сборка имеет строгое имя.</span><span class="sxs-lookup"><span data-stu-id="a7e53-132">Forces an update even if the assembly is strong-named.</span></span> <span data-ttu-id="a7e53-133">**Важно!** При обновлении сборки со строгим именем перед выполнением ее кода необходимо снова подписать сборку.</span><span class="sxs-lookup"><span data-stu-id="a7e53-133">**Important:**  If you update a strong-named assembly, you must sign it again before executing its code.</span></span>|  
|<span data-ttu-id="a7e53-134">**/help**</span><span class="sxs-lookup"><span data-stu-id="a7e53-134">**/help**</span></span>|<span data-ttu-id="a7e53-135">Отображает синтаксис команд и параметров программы.</span><span class="sxs-lookup"><span data-stu-id="a7e53-135">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="a7e53-136">**/ILONLY+**</span><span class="sxs-lookup"><span data-stu-id="a7e53-136">**/ILONLY+**</span></span>|<span data-ttu-id="a7e53-137">Устанавливает флаг ILONLY.</span><span class="sxs-lookup"><span data-stu-id="a7e53-137">Sets the ILONLY flag.</span></span>|  
|<span data-ttu-id="a7e53-138">**/ILONLY-**</span><span class="sxs-lookup"><span data-stu-id="a7e53-138">**/ILONLY-**</span></span>|<span data-ttu-id="a7e53-139">Снимает флаг ILONLY.</span><span class="sxs-lookup"><span data-stu-id="a7e53-139">Clears the ILONLY flag.</span></span>|  
|<span data-ttu-id="a7e53-140">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="a7e53-140">**/nologo**</span></span>|<span data-ttu-id="a7e53-141">Отключает отображение эмблемы Майкрософт при запуске.</span><span class="sxs-lookup"><span data-stu-id="a7e53-141">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="a7e53-142">**/RevertCLRHeader**</span><span class="sxs-lookup"><span data-stu-id="a7e53-142">**/RevertCLRHeader**</span></span>|<span data-ttu-id="a7e53-143">Задает версии заголовка CLR значение 2.0.</span><span class="sxs-lookup"><span data-stu-id="a7e53-143">Reverts the CLR header version to 2.0.</span></span>|  
|<span data-ttu-id="a7e53-144">**/ UpgradeCLRHeader**</span><span class="sxs-lookup"><span data-stu-id="a7e53-144">**/UpgradeCLRHeader**</span></span>|<span data-ttu-id="a7e53-145">Обновляет версию заголовка CLR до версии 2.5.</span><span class="sxs-lookup"><span data-stu-id="a7e53-145">Upgrades the CLR header version to 2.5.</span></span> <span data-ttu-id="a7e53-146">**Примечание.** Для оптимального выполнения сборок они должны иметь версию заголовка CLR 2.5 или выше.</span><span class="sxs-lookup"><span data-stu-id="a7e53-146">**Note:**  Assemblies must have a CLR header version of 2.5 or greater to run natively.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7e53-147">Примечания</span><span class="sxs-lookup"><span data-stu-id="a7e53-147">Remarks</span></span>  
 <span data-ttu-id="a7e53-148">Если другие параметры не заданы, средство преобразования CorFlags отображает флаги заданной сборки.</span><span class="sxs-lookup"><span data-stu-id="a7e53-148">If no options are specified, the CorFlags Conversion tool displays the flags for the specified assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7e53-149">См. также</span><span class="sxs-lookup"><span data-stu-id="a7e53-149">See Also</span></span>  
 [<span data-ttu-id="a7e53-150">Инструменты</span><span class="sxs-lookup"><span data-stu-id="a7e53-150">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="a7e53-151">64-разрядные приложения</span><span class="sxs-lookup"><span data-stu-id="a7e53-151">64-bit Applications</span></span>](../../../docs/framework/64-bit-apps.md)  
 [<span data-ttu-id="a7e53-152">Командные строки</span><span class="sxs-lookup"><span data-stu-id="a7e53-152">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
