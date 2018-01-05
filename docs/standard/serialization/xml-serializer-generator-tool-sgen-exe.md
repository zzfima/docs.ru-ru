---
title: "Инструмент создания XML-сериализатора (Sgen.exe)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc1d1f1c-fb26-4be9-885a-3fe84c81cec6
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 005e78c32d49c8c1b204a3ac9376d943311868fd
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="xml-serializer-generator-tool-sgenexe"></a><span data-ttu-id="c4612-102">Инструмент создания XML-сериализатора (Sgen.exe)</span><span class="sxs-lookup"><span data-stu-id="c4612-102">XML Serializer Generator Tool (Sgen.exe)</span></span>
<span data-ttu-id="c4612-103">Генератор XML-сериализатора создает сборку сериализации XML для типов в указанной сборке, чтобы повысить производительность при запуске <xref:System.Xml.Serialization.XmlSerializer> во время сериализации или десериализации объектов указанных типов.</span><span class="sxs-lookup"><span data-stu-id="c4612-103">The XML Serializer Generator creates an XML serialization assembly for types in a specified assembly in order to improve the startup performance of a <xref:System.Xml.Serialization.XmlSerializer> when it serializes or deserializes objects of the specified types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4612-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4612-104">Syntax</span></span>  
  
```  
sgen [options]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c4612-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c4612-105">Parameters</span></span>  
  
|<span data-ttu-id="c4612-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="c4612-106">Option</span></span>|<span data-ttu-id="c4612-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="c4612-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c4612-108">**/a**[**ssembly**]**:***имя_файла*</span><span class="sxs-lookup"><span data-stu-id="c4612-108">**/a**[**ssembly**]**:***filename*</span></span>|<span data-ttu-id="c4612-109">Создает код сериализации для всех типов, содержащихся в сборке, или исполняемого файла *имя_файла*.</span><span class="sxs-lookup"><span data-stu-id="c4612-109">Generates serialization code for all the types contained in the assembly or executable specified by *filename*.</span></span> <span data-ttu-id="c4612-110">Можно указать только одно имя файла.</span><span class="sxs-lookup"><span data-stu-id="c4612-110">Only one file name can be provided.</span></span> <span data-ttu-id="c4612-111">Если этот аргумент повторяется, используется последнее имя файла.</span><span class="sxs-lookup"><span data-stu-id="c4612-111">If this argument is repeated, the last file name is used.</span></span>|  
|<span data-ttu-id="c4612-112">**/c[ompiler]:** *параметры*</span><span class="sxs-lookup"><span data-stu-id="c4612-112">**/c[ompiler]:** *options*</span></span>|<span data-ttu-id="c4612-113">Задает параметры, которые следует передать компилятору C#.</span><span class="sxs-lookup"><span data-stu-id="c4612-113">Specifies the options to pass to the C# compiler.</span></span> <span data-ttu-id="c4612-114">Поддерживаются все параметры csc.exe по мере их передачи компилятору.</span><span class="sxs-lookup"><span data-stu-id="c4612-114">All csc.exe options are supported as they are passed to the compiler.</span></span> <span data-ttu-id="c4612-115">Этот параметр можно использовать для указания того, что сборка должна быть подписана, и для указания файла ключа.</span><span class="sxs-lookup"><span data-stu-id="c4612-115">This can be used to specify that the assembly should be signed and to specify the key file.</span></span>|  
|<span data-ttu-id="c4612-116">**/d**[**ebug**]</span><span class="sxs-lookup"><span data-stu-id="c4612-116">**/d**[**ebug**]</span></span>|<span data-ttu-id="c4612-117">Создает образ, который может использоваться с отладчиком.</span><span class="sxs-lookup"><span data-stu-id="c4612-117">Generates an image that can be used with a debugger.</span></span>|  
|<span data-ttu-id="c4612-118">**/f[orce]**</span><span class="sxs-lookup"><span data-stu-id="c4612-118">**/f[orce]**</span></span>|<span data-ttu-id="c4612-119">Принудительно перезаписывает существующую сборку с одинаковым именем.</span><span class="sxs-lookup"><span data-stu-id="c4612-119">Forces the overwriting of an existing assembly of the same name.</span></span> <span data-ttu-id="c4612-120">Значение по умолчанию — **false**.</span><span class="sxs-lookup"><span data-stu-id="c4612-120">The default is **false**.</span></span>|  
|<span data-ttu-id="c4612-121">**/help или /?**</span><span class="sxs-lookup"><span data-stu-id="c4612-121">**/help or /?**</span></span>|<span data-ttu-id="c4612-122">Отображает синтаксис команд и параметров программы.</span><span class="sxs-lookup"><span data-stu-id="c4612-122">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="c4612-123">**/k**[**eep**]</span><span class="sxs-lookup"><span data-stu-id="c4612-123">**/k**[**eep**]</span></span>|<span data-ttu-id="c4612-124">Предотвращает удаление созданных исходных файлов и других временных файлов после их компиляции в сборку сериализации.</span><span class="sxs-lookup"><span data-stu-id="c4612-124">Suppresses the deletion of the generated source files and other temporary files after they have been compiled into the serialization assembly.</span></span> <span data-ttu-id="c4612-125">Этот параметр можно использовать, чтобы определить, создает ли инструмент код сериализации для определенного типа.</span><span class="sxs-lookup"><span data-stu-id="c4612-125">This can be used to determine whether the tool is generating serialization code for a particular type.</span></span>|  
|<span data-ttu-id="c4612-126">**/n**[**ologo**]</span><span class="sxs-lookup"><span data-stu-id="c4612-126">**/n**[**ologo**]</span></span>|<span data-ttu-id="c4612-127">Отключает отображение эмблемы Майкрософт при запуске.</span><span class="sxs-lookup"><span data-stu-id="c4612-127">Suppresses the display of the Microsoft startup banner.</span></span>|  
|<span data-ttu-id="c4612-128">**/o**[**ut**]**:***путь*</span><span class="sxs-lookup"><span data-stu-id="c4612-128">**/o**[**ut**]**:***path*</span></span>|<span data-ttu-id="c4612-129">Определяет каталог, в которой сохраняется созданная сборка.</span><span class="sxs-lookup"><span data-stu-id="c4612-129">Specifies the directory in which to save the generated assembly.</span></span> <span data-ttu-id="c4612-130">**Примечание**. Имя созданной сборки представляет собой имя входной сборки и "xmlSerializers.dll".</span><span class="sxs-lookup"><span data-stu-id="c4612-130">**Note:**  The name of the generated assembly is composed of the name of the input assembly plus "xmlSerializers.dll".</span></span>|  
|<span data-ttu-id="c4612-131">**/p**[**roxytypes**]</span><span class="sxs-lookup"><span data-stu-id="c4612-131">**/p**[**roxytypes**]</span></span>|<span data-ttu-id="c4612-132">Создает код сериализации только для типов прокси XML-веб-службы.</span><span class="sxs-lookup"><span data-stu-id="c4612-132">Generates serialization code only for the XML Web service proxy types.</span></span>|  
|<span data-ttu-id="c4612-133">**/r**[**eference**]**:***файлы_сборки*</span><span class="sxs-lookup"><span data-stu-id="c4612-133">**/r**[**eference**]**:***assemblyfiles*</span></span>|<span data-ttu-id="c4612-134">Задает сборки, на которые ссылаются типы, требующие XML-сериализации.</span><span class="sxs-lookup"><span data-stu-id="c4612-134">Specifies the assemblies that are referenced by the types requiring XML serialization.</span></span> <span data-ttu-id="c4612-135">Принимает несколько файлов сборки, которые разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="c4612-135">Accepts multiple assembly files separated by commas.</span></span>|  
|<span data-ttu-id="c4612-136">**/s**[**ilent**]</span><span class="sxs-lookup"><span data-stu-id="c4612-136">**/s**[**ilent**]</span></span>|<span data-ttu-id="c4612-137">Запрещает отображение сообщений об успешно выполненных операциях.</span><span class="sxs-lookup"><span data-stu-id="c4612-137">Suppresses the display of success messages.</span></span>|  
|<span data-ttu-id="c4612-138">**/t**[**ype**]**:***тип*</span><span class="sxs-lookup"><span data-stu-id="c4612-138">**/t**[**ype**]**:***type*</span></span>|<span data-ttu-id="c4612-139">Создает код сериализации только для указанного типа.</span><span class="sxs-lookup"><span data-stu-id="c4612-139">Generates serialization code only for the specified type.</span></span>|  
|<span data-ttu-id="c4612-140">**/v**[**erbose**]</span><span class="sxs-lookup"><span data-stu-id="c4612-140">**/v**[**erbose**]</span></span>|<span data-ttu-id="c4612-141">Отображает подробную выходную информацию для отладки.</span><span class="sxs-lookup"><span data-stu-id="c4612-141">Displays verbose output for debugging.</span></span> <span data-ttu-id="c4612-142">Содержит список типов из целевой сборки, которые невозможно сериализовать с помощью <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="c4612-142">Lists types from the target assembly that cannot be serialized with the <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|  
|<span data-ttu-id="c4612-143">**/?**</span><span class="sxs-lookup"><span data-stu-id="c4612-143">**/?**</span></span>|<span data-ttu-id="c4612-144">Отображает синтаксис команд и параметров программы.</span><span class="sxs-lookup"><span data-stu-id="c4612-144">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4612-145">Примечания</span><span class="sxs-lookup"><span data-stu-id="c4612-145">Remarks</span></span>  
 <span data-ttu-id="c4612-146">Если генератор XML-сериализатора не используется, <xref:System.Xml.Serialization.XmlSerializer> создает код сериализации и сборку сериализации для каждого типа при каждом запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="c4612-146">When the XML Serializer Generator is not used, a <xref:System.Xml.Serialization.XmlSerializer> generates serialization code and a serialization assembly for each type every time an application is run.</span></span> <span data-ttu-id="c4612-147">Для повышения производительности при запуске XML-сериализации используйте инструмент Sgen.exe, чтобы создать такие сборки заранее.</span><span class="sxs-lookup"><span data-stu-id="c4612-147">To improve the performance of XML serialization startup, use the Sgen.exe tool to generate those assemblies the assemblies in advance.</span></span> <span data-ttu-id="c4612-148">Эти сборки можно развернуть вместе с приложением.</span><span class="sxs-lookup"><span data-stu-id="c4612-148">These assemblies can then be deployed with the application.</span></span>  
  
 <span data-ttu-id="c4612-149">Инструмент создания XML-сериализатора также повышает производительность клиентов, использующих прокси XML-веб-служб для связи с серверами, поскольку производительность процесса сериализации не снижается при первой загрузке типа.</span><span class="sxs-lookup"><span data-stu-id="c4612-149">The XML Serializer Generator can also improve the performance of clients that use XML Web service proxies to communicate with servers because the serialization process will not incur a performance hit when the type is loaded the first time.</span></span>  
  
 <span data-ttu-id="c4612-150">Эти созданные сборки нельзя использовать на стороне сервера веб-службы.</span><span class="sxs-lookup"><span data-stu-id="c4612-150">These generated assemblies cannot be used on the server side of a Web service.</span></span> <span data-ttu-id="c4612-151">Этот инструмент предназначен только для клиентов веб-служб и сценариев ручной сериализации.</span><span class="sxs-lookup"><span data-stu-id="c4612-151">This tool is only for Web service clients and manual serialization scenarios.</span></span>  
  
 <span data-ttu-id="c4612-152">Если сборка, содержащая сериализуемый тип, называется "MyType.dll", связанная сборка сериализации будет называться "MyType.XmlSerializers.dll".</span><span class="sxs-lookup"><span data-stu-id="c4612-152">If the assembly containing the type to serialize is named MyType.dll, then the associated serialization assembly will be named MyType.XmlSerializers.dll.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c4612-153">Примеры</span><span class="sxs-lookup"><span data-stu-id="c4612-153">Examples</span></span>  
 <span data-ttu-id="c4612-154">Следующая команда создает сборку с именем "Data.XmlSerializers.dll" для сериализации всех типов, содержащихся в сборке с именем "Data.dll".</span><span class="sxs-lookup"><span data-stu-id="c4612-154">The following command creates an assembly named Data.XmlSerializers.dll for serializing all the types contained in the assembly named Data.dll.</span></span>  
  
```  
sgen Data.dll   
```  
  
 <span data-ttu-id="c4612-155">Код, для которого требуется сериализация и десериализация типов в Data.dll, может содержать ссылки на сборку Data.XmlSerializers.dll.</span><span class="sxs-lookup"><span data-stu-id="c4612-155">The Data.XmlSerializers.dll assembly can be referenced from code that needs to serialize and deserialize the types in Data.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4612-156">См. также</span><span class="sxs-lookup"><span data-stu-id="c4612-156">See Also</span></span>  
 [<span data-ttu-id="c4612-157">Инструменты</span><span class="sxs-lookup"><span data-stu-id="c4612-157">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="c4612-158">Обзор веб-служб XML</span><span class="sxs-lookup"><span data-stu-id="c4612-158">XML Web Services Overview</span></span>](http://msdn.microsoft.com/en-us/9db0c7b8-bca6-462b-9be5-f5f9a7f05a4d)  
 [<span data-ttu-id="c4612-159">Командные строки</span><span class="sxs-lookup"><span data-stu-id="c4612-159">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
