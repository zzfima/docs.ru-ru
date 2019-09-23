---
title: CorFlags.exe (средство преобразования CorFlags)
ms.date: 03/30/2017
helpviewer_keywords:
- CorFlags conversion tool
- CorFlags.exe
- portable executable files, CorFlags section
ms.assetid: ef900f8f-71ca-4dde-9b8c-95ddb0d7d89c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b420fb451bf1bb2078a4419a648a1407c39ad178
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71044743"
---
# <a name="corflagsexe-corflags-conversion-tool"></a><span data-ttu-id="cdc3c-102">CorFlags.exe (средство преобразования CorFlags)</span><span class="sxs-lookup"><span data-stu-id="cdc3c-102">CorFlags.exe (CorFlags Conversion Tool)</span></span>
<span data-ttu-id="cdc3c-103">Средство преобразования CorFlags позволяет настраивать раздел CorFlags в заголовке переносимого исполняемого образа.</span><span class="sxs-lookup"><span data-stu-id="cdc3c-103">The CorFlags Conversion tool allows you to configure the CorFlags section of the header of a portable executable image.</span></span>  
  
 <span data-ttu-id="cdc3c-104">Эта программа автоматически устанавливается вместе с Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cdc3c-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="cdc3c-105">Чтобы применить этот инструмент, воспользуйтесь командной строкой разработчика для Visual Studio (или командной строкой Visual Studio в Windows 7).</span><span class="sxs-lookup"><span data-stu-id="cdc3c-105">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="cdc3c-106">Дополнительные сведения см. в разделе [Командные строки](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="cdc3c-106">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="cdc3c-107">В командной строке введите следующее.</span><span class="sxs-lookup"><span data-stu-id="cdc3c-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdc3c-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cdc3c-108">Syntax</span></span>  
  
```console  
CorFlags.exe assembly [options]  
```  
  
## <a name="parameters"></a><span data-ttu-id="cdc3c-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="cdc3c-109">Parameters</span></span>  
  
|<span data-ttu-id="cdc3c-110">Обязательный параметр</span><span class="sxs-lookup"><span data-stu-id="cdc3c-110">Required parameter</span></span>|<span data-ttu-id="cdc3c-111">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="cdc3c-111">Description</span></span>|  
|------------------------|-----------------|  
|`assembly`|<span data-ttu-id="cdc3c-112">Имя сборки, для которой требуется настроить раздел CorFlags.</span><span class="sxs-lookup"><span data-stu-id="cdc3c-112">The name of the assembly for which to configure the CorFlags.</span></span>|  
  
|<span data-ttu-id="cdc3c-113">Параметр</span><span class="sxs-lookup"><span data-stu-id="cdc3c-113">Option</span></span>|<span data-ttu-id="cdc3c-114">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="cdc3c-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="cdc3c-115">**/32BIT[REQ]+**</span><span class="sxs-lookup"><span data-stu-id="cdc3c-115">**/32BIT[REQ]+**</span></span>|<span data-ttu-id="cdc3c-116">Устанавливает флаг 32BITREQUIRED.</span><span class="sxs-lookup"><span data-stu-id="cdc3c-116">Sets the 32BITREQUIRED flag.</span></span>|  
|<span data-ttu-id="cdc3c-117">**/32BIT[REQ]-**</span><span class="sxs-lookup"><span data-stu-id="cdc3c-117">**/32BIT[REQ]-**</span></span>|<span data-ttu-id="cdc3c-118">Снимает флаг 32BITREQUIRED.</span><span class="sxs-lookup"><span data-stu-id="cdc3c-118">Clears the 32BITREQUIRED flag.</span></span>|  
|<span data-ttu-id="cdc3c-119">**/32BITPREF+**</span><span class="sxs-lookup"><span data-stu-id="cdc3c-119">**/32BITPREF+**</span></span>|<span data-ttu-id="cdc3c-120">Устанавливает флаг 32BITPREFERRED.</span><span class="sxs-lookup"><span data-stu-id="cdc3c-120">Sets the 32BITPREFERRED flag.</span></span> <span data-ttu-id="cdc3c-121">Приложение выполняется как 32-разрядный процесс даже на 64-разрядных платформах.</span><span class="sxs-lookup"><span data-stu-id="cdc3c-121">The app runs as a 32-bit process even on 64-bit platforms.</span></span> <span data-ttu-id="cdc3c-122">Устанавливайте этот флаг только в EXE-файлах.</span><span class="sxs-lookup"><span data-stu-id="cdc3c-122">Set this flag only on EXE files.</span></span> <span data-ttu-id="cdc3c-123">Если флаг установлен для библиотеки DLL, она не загружается в 64-разрядных процессах и создается исключение <xref:System.BadImageFormatException>.</span><span class="sxs-lookup"><span data-stu-id="cdc3c-123">If the flag is set on a DLL, the DLL fails to load in 64-bit processes, and a <xref:System.BadImageFormatException> exception is thrown.</span></span> <span data-ttu-id="cdc3c-124">Файл EXE с этим флагом можно загрузить в 64-разрядный процесс.</span><span class="sxs-lookup"><span data-stu-id="cdc3c-124">An EXE file with this flag can be loaded into a 64-bit process.</span></span><br /><br /> <span data-ttu-id="cdc3c-125">Новые возможности .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="cdc3c-125">New in the .NET Framework 4.5.</span></span>|  
|<span data-ttu-id="cdc3c-126">**/32BITPREF-**</span><span class="sxs-lookup"><span data-stu-id="cdc3c-126">**/32BITPREF-**</span></span>|<span data-ttu-id="cdc3c-127">Снимает флаг 32BITPREFERRED.</span><span class="sxs-lookup"><span data-stu-id="cdc3c-127">Clears the 32BITPREFERRED flag.</span></span><br /><br /> <span data-ttu-id="cdc3c-128">Новые возможности .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="cdc3c-128">New in the .NET Framework 4.5.</span></span>|  
|<span data-ttu-id="cdc3c-129">**/?**</span><span class="sxs-lookup"><span data-stu-id="cdc3c-129">**/?**</span></span>|<span data-ttu-id="cdc3c-130">Отображает синтаксис команд и параметров программы.</span><span class="sxs-lookup"><span data-stu-id="cdc3c-130">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="cdc3c-131">**/Force**</span><span class="sxs-lookup"><span data-stu-id="cdc3c-131">**/Force**</span></span>|<span data-ttu-id="cdc3c-132">Выполняет принудительное обновление, даже если сборка имеет строгое имя.</span><span class="sxs-lookup"><span data-stu-id="cdc3c-132">Forces an update even if the assembly is strong-named.</span></span> <span data-ttu-id="cdc3c-133">**Внимание!**  При обновлении сборки со строгим именем перед выполнением ее кода необходимо снова подписать сборку.</span><span class="sxs-lookup"><span data-stu-id="cdc3c-133">**Important:**  If you update a strong-named assembly, you must sign it again before executing its code.</span></span>|  
|<span data-ttu-id="cdc3c-134">**/help**</span><span class="sxs-lookup"><span data-stu-id="cdc3c-134">**/help**</span></span>|<span data-ttu-id="cdc3c-135">Отображает синтаксис команд и параметров программы.</span><span class="sxs-lookup"><span data-stu-id="cdc3c-135">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="cdc3c-136">**/ILONLY+**</span><span class="sxs-lookup"><span data-stu-id="cdc3c-136">**/ILONLY+**</span></span>|<span data-ttu-id="cdc3c-137">Устанавливает флаг ILONLY.</span><span class="sxs-lookup"><span data-stu-id="cdc3c-137">Sets the ILONLY flag.</span></span>|  
|<span data-ttu-id="cdc3c-138">**/ILONLY-**</span><span class="sxs-lookup"><span data-stu-id="cdc3c-138">**/ILONLY-**</span></span>|<span data-ttu-id="cdc3c-139">Снимает флаг ILONLY.</span><span class="sxs-lookup"><span data-stu-id="cdc3c-139">Clears the ILONLY flag.</span></span>|  
|<span data-ttu-id="cdc3c-140">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="cdc3c-140">**/nologo**</span></span>|<span data-ttu-id="cdc3c-141">Отключает отображение эмблемы Майкрософт при запуске.</span><span class="sxs-lookup"><span data-stu-id="cdc3c-141">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="cdc3c-142">**/RevertCLRHeader**</span><span class="sxs-lookup"><span data-stu-id="cdc3c-142">**/RevertCLRHeader**</span></span>|<span data-ttu-id="cdc3c-143">Задает версии заголовка CLR значение 2.0.</span><span class="sxs-lookup"><span data-stu-id="cdc3c-143">Reverts the CLR header version to 2.0.</span></span>|  
|<span data-ttu-id="cdc3c-144">**/ UpgradeCLRHeader**</span><span class="sxs-lookup"><span data-stu-id="cdc3c-144">**/UpgradeCLRHeader**</span></span>|<span data-ttu-id="cdc3c-145">Обновляет версию заголовка CLR до версии 2.5.</span><span class="sxs-lookup"><span data-stu-id="cdc3c-145">Upgrades the CLR header version to 2.5.</span></span> <span data-ttu-id="cdc3c-146">**Примечание.**  Для оптимального выполнения сборок они должны иметь версию заголовка CLR 2.5.</span><span class="sxs-lookup"><span data-stu-id="cdc3c-146">**Note:**  Assemblies must have a CLR header version of 2.5 or greater to run natively.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cdc3c-147">Примечания</span><span class="sxs-lookup"><span data-stu-id="cdc3c-147">Remarks</span></span>  
 <span data-ttu-id="cdc3c-148">Если другие параметры не заданы, средство преобразования CorFlags отображает флаги заданной сборки.</span><span class="sxs-lookup"><span data-stu-id="cdc3c-148">If no options are specified, the CorFlags Conversion tool displays the flags for the specified assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdc3c-149">См. также</span><span class="sxs-lookup"><span data-stu-id="cdc3c-149">See also</span></span>

- [<span data-ttu-id="cdc3c-150">Инструменты</span><span class="sxs-lookup"><span data-stu-id="cdc3c-150">Tools</span></span>](index.md)
- [<span data-ttu-id="cdc3c-151">64-разрядные приложения</span><span class="sxs-lookup"><span data-stu-id="cdc3c-151">64-bit Applications</span></span>](../64-bit-apps.md)
- [<span data-ttu-id="cdc3c-152">Командные строки</span><span class="sxs-lookup"><span data-stu-id="cdc3c-152">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
