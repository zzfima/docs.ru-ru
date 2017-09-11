---
title: "Практическое руководство. Использование XML-документации (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: eeee77db523bc0ad97f425d4ba8076ae5740dfe8
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-the-xml-documentation-features-c-programming-guide"></a><span data-ttu-id="e3a0c-102">Практическое руководство. Использование XML-документации (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="e3a0c-102">How to: Use the XML Documentation Features (C# Programming Guide)</span></span>
<span data-ttu-id="e3a0c-103">В данном примере представлены основные общие сведения о задокументированном типе.</span><span class="sxs-lookup"><span data-stu-id="e3a0c-103">The following sample provides a basic overview of a type that has been documented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3a0c-104">Пример</span><span class="sxs-lookup"><span data-stu-id="e3a0c-104">Example</span></span>  
 <span data-ttu-id="e3a0c-105">[!code-cs[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e3a0c-105">[!code-cs[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]</span></span>  
  
 <span data-ttu-id="e3a0c-106">**// Этот XML-файл был создан в предыдущем образце кода.**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-106">**// This .xml file was generated with the previous code sample.**</span></span>  
<span data-ttu-id="e3a0c-107">**\<?xml version="1.0"?>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-107">**\<?xml version="1.0"?>**</span></span>  
<span data-ttu-id="e3a0c-108">**\<doc>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-108">**\<doc>**</span></span>  
 <span data-ttu-id="e3a0c-109">**\<assembly>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-109">**\<assembly>**</span></span>  
 <span data-ttu-id="e3a0c-110">**\<name>xmlsample\</name>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-110">**\<name>xmlsample\</name>**</span></span>  
 <span data-ttu-id="e3a0c-111">**\</assembly>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-111">**\</assembly>**</span></span>  
 <span data-ttu-id="e3a0c-112">**\<members>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-112">**\<members>**</span></span>  
 <span data-ttu-id="e3a0c-113">**\<member name="T:SomeClass">**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-113">**\<member name="T:SomeClass">**</span></span>  
 <span data-ttu-id="e3a0c-114">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-114">**\<summary>**</span></span>  
 <span data-ttu-id="e3a0c-115">**Здесь сводная документация об уровне класса.\</summary>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-115">**Class level summary documentation goes here.\</summary>**</span></span>  
 <span data-ttu-id="e3a0c-116">**\<remarks>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-116">**\<remarks>**</span></span>  
 <span data-ttu-id="e3a0c-117">**Расширенные комментарии можно связать с типом или членом** </span><span class="sxs-lookup"><span data-stu-id="e3a0c-117">**Longer comments can be associated with a type or member** </span></span>  
 <span data-ttu-id="e3a0c-118">**при помощи тега remarks\</remarks>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-118">**through the remarks tag\</remarks>**</span></span>  
 <span data-ttu-id="e3a0c-119">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-119">**\</member>**</span></span>  
 <span data-ttu-id="e3a0c-120">**\<member name="F:SomeClass.m_Name">**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-120">**\<member name="F:SomeClass.m_Name">**</span></span>  
 <span data-ttu-id="e3a0c-121">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-121">**\<summary>**</span></span>  
 <span data-ttu-id="e3a0c-122">**Хранилище для свойства name\</summary>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-122">**Store for the name property\</summary>**</span></span>  
 <span data-ttu-id="e3a0c-123">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-123">**\</member>**</span></span>  
 <span data-ttu-id="e3a0c-124">**\<member name="M:SomeClass.#ctor">**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-124">**\<member name="M:SomeClass.#ctor">**</span></span>  
 <span data-ttu-id="e3a0c-125">**\<summary>Конструктор класса.\</summary>** </span><span class="sxs-lookup"><span data-stu-id="e3a0c-125">**\<summary>The class constructor.\</summary>** </span></span>  
 <span data-ttu-id="e3a0c-126">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-126">**\</member>**</span></span>  
 <span data-ttu-id="e3a0c-127">**\<member name="M:SomeClass.SomeMethod(System.String)">**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-127">**\<member name="M:SomeClass.SomeMethod(System.String)">**</span></span>  
 <span data-ttu-id="e3a0c-128">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-128">**\<summary>**</span></span>  
 <span data-ttu-id="e3a0c-129">**Описание метода SomeMethod.\</summary>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-129">**Description for SomeMethod.\</summary>**</span></span>  
 <span data-ttu-id="e3a0c-130">**\<param name="s"> Здесь описание параметра s\</param>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-130">**\<param name="s"> Parameter description for s goes here\</param>**</span></span>  
 <span data-ttu-id="e3a0c-131">**\<seealso cref="T:System.String">**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-131">**\<seealso cref="T:System.String">**</span></span>  
 <span data-ttu-id="e3a0c-132">**Атрибут cref можно использовать в любом теге для ссылки на тип или член,** </span><span class="sxs-lookup"><span data-stu-id="e3a0c-132">**You can use the cref attribute on any tag to reference a type or member** </span></span>  
 <span data-ttu-id="e3a0c-133">**и тогда компилятор проверит существование ссылки. \</seealso>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-133">**and the compiler will check that the reference exists. \</seealso>**</span></span>  
 <span data-ttu-id="e3a0c-134">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-134">**\</member>**</span></span>  
 <span data-ttu-id="e3a0c-135">**\<member name="M:SomeClass.SomeOtherMethod">**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-135">**\<member name="M:SomeClass.SomeOtherMethod">**</span></span>  
 <span data-ttu-id="e3a0c-136">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-136">**\<summary>**</span></span>  
 <span data-ttu-id="e3a0c-137">**Какой-либо другой метод. \</summary>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-137">**Some other method. \</summary>**</span></span>  
 <span data-ttu-id="e3a0c-138">**\<returns>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-138">**\<returns>**</span></span>  
 <span data-ttu-id="e3a0c-139">**Возврат результатов, описанных при помощи тега returns.\</returns>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-139">**Return results are described through the returns tag.\</returns>**</span></span>  
 <span data-ttu-id="e3a0c-140">**\<seealso cref="M:SomeClass.SomeMethod(System.String)">**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-140">**\<seealso cref="M:SomeClass.SomeMethod(System.String)">**</span></span>  
 <span data-ttu-id="e3a0c-141">**Обратите внимание, что атрибут cref используется для ссылки на указанный метод \</seealso>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-141">**Notice the use of the cref attribute to reference a specific method \</seealso>**</span></span>  
 <span data-ttu-id="e3a0c-142">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-142">**\</member>**</span></span>  
 <span data-ttu-id="e3a0c-143">**\<member name="M:SomeClass.Main(System.String[])">**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-143">**\<member name="M:SomeClass.Main(System.String[])">**</span></span>  
 <span data-ttu-id="e3a0c-144">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-144">**\<summary>**</span></span>  
 <span data-ttu-id="e3a0c-145">**Точка входа для приложения.**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-145">**The entry point for the application.**</span></span>  
 <span data-ttu-id="e3a0c-146">**\</summary>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-146">**\</summary>**</span></span>  
 <span data-ttu-id="e3a0c-147">**\<param name="args"> Список аргументов командной строки\</param>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-147">**\<param name="args"> A list of command line arguments\</param>**</span></span>  
 <span data-ttu-id="e3a0c-148">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-148">**\</member>**</span></span>  
 <span data-ttu-id="e3a0c-149">**\<member name="P:SomeClass.Name">**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-149">**\<member name="P:SomeClass.Name">**</span></span>  
 <span data-ttu-id="e3a0c-150">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-150">**\<summary>**</span></span>  
 <span data-ttu-id="e3a0c-151">**Свойство Name \</summary>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-151">**Name property \</summary>**</span></span>  
 <span data-ttu-id="e3a0c-152">**\<value>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-152">**\<value>**</span></span>  
 <span data-ttu-id="e3a0c-153">**Тег value используется для описания значения свойства\</value>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-153">**A value tag is used to describe the property value\</value>**</span></span>  
 <span data-ttu-id="e3a0c-154">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-154">**\</member>**</span></span>  
 <span data-ttu-id="e3a0c-155">**\</members>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-155">**\</members>**</span></span>  
<span data-ttu-id="e3a0c-156">**\</doc>**</span><span class="sxs-lookup"><span data-stu-id="e3a0c-156">**\</doc>**</span></span>   
## <a name="compiling-the-code"></a><span data-ttu-id="e3a0c-157">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="e3a0c-157">Compiling the Code</span></span>  
 <span data-ttu-id="e3a0c-158">Чтобы скомпилировать этот пример, введите в командной строке:</span><span class="sxs-lookup"><span data-stu-id="e3a0c-158">To compile the example, type the following command line:</span></span>  
  
 `csc XMLsample.cs /doc:XMLsample.xml`  
  
 <span data-ttu-id="e3a0c-159">Эта команда создает XML-файл XMLsample.xml, который можно просмотреть в браузере или с помощью команды TYPE.</span><span class="sxs-lookup"><span data-stu-id="e3a0c-159">This will create the XML file XMLsample.xml, which you can view in your browser or by using the TYPE command.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e3a0c-160">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="e3a0c-160">Robust Programming</span></span>  
 <span data-ttu-id="e3a0c-161">Документация XML начинается с ///.</span><span class="sxs-lookup"><span data-stu-id="e3a0c-161">XML documentation starts with ///.</span></span> <span data-ttu-id="e3a0c-162">При создании нового проекта мастер добавляет несколько строк ///.</span><span class="sxs-lookup"><span data-stu-id="e3a0c-162">When you create a new project, the wizards put some starter /// lines in for you.</span></span> <span data-ttu-id="e3a0c-163">Обработка этих комментариев имеет некоторые ограничения.</span><span class="sxs-lookup"><span data-stu-id="e3a0c-163">The processing of these comments has some restrictions:</span></span>  
  
-   <span data-ttu-id="e3a0c-164">Документация должна представлять собой XML с правильным форматом.</span><span class="sxs-lookup"><span data-stu-id="e3a0c-164">The documentation must be well-formed XML.</span></span> <span data-ttu-id="e3a0c-165">Если формат XML неверен, то выдается предупреждение и файл документации содержит комментарий о том, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="e3a0c-165">If the XML is not well-formed, a warning is generated and the documentation file will contain a comment that says that an error was encountered.</span></span>  
  
-   <span data-ttu-id="e3a0c-166">Разработчики могут создавать собственные наборы тегов.</span><span class="sxs-lookup"><span data-stu-id="e3a0c-166">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="e3a0c-167">Однако существует рекомендуемый набор тегов (см. раздел "См. также" в данной теме).</span><span class="sxs-lookup"><span data-stu-id="e3a0c-167">There is a recommended set of tags (see the Further Reading section).</span></span> <span data-ttu-id="e3a0c-168">Некоторые рекомендуемые теги имеют особые значения.</span><span class="sxs-lookup"><span data-stu-id="e3a0c-168">Some of the recommended tags have special meanings:</span></span>  
  
    -   <span data-ttu-id="e3a0c-169">Тег \<param> используется для описания параметров.</span><span class="sxs-lookup"><span data-stu-id="e3a0c-169">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="e3a0c-170">При использовании этого тега компилятор проверяет, что параметр существует и все параметры описаны в документации.</span><span class="sxs-lookup"><span data-stu-id="e3a0c-170">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="e3a0c-171">При сбое проверки компилятор выдает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="e3a0c-171">If the verification failed, the compiler issues a warning.</span></span>  
  
    -   <span data-ttu-id="e3a0c-172">Атрибут `cref` может быть присоединен к любому тегу для предоставления ссылки на элемент кода.</span><span class="sxs-lookup"><span data-stu-id="e3a0c-172">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="e3a0c-173">Компилятор проверяет наличие этого элемента кода.</span><span class="sxs-lookup"><span data-stu-id="e3a0c-173">The compiler will verify that this code element exists.</span></span> <span data-ttu-id="e3a0c-174">При сбое проверки компилятор выдает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="e3a0c-174">If the verification failed, the compiler issues a warning.</span></span> <span data-ttu-id="e3a0c-175">Компилятор учитывает любые операторы `using` при поиске типа, описанного в атрибуте `cref`.</span><span class="sxs-lookup"><span data-stu-id="e3a0c-175">The compiler respects any `using` statements when it looks for a type described in the `cref` attribute.</span></span>  
  
    -   <span data-ttu-id="e3a0c-176">Тег \<summary> используется технологией IntelliSense в Visual Studio для отображения дополнительных сведений о типе или члене.</span><span class="sxs-lookup"><span data-stu-id="e3a0c-176">The \<summary> tag is used by IntelliSense inside Visual Studio to display additional information about a type or member.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="e3a0c-177">XML-файл не предоставляет полную информацию о типе и членах (например, он не содержит никаких сведений о типе).</span><span class="sxs-lookup"><span data-stu-id="e3a0c-177">The XML file does not provide full information about the type and members (for example, it does not contain any type information).</span></span> <span data-ttu-id="e3a0c-178">Чтобы получить полную информацию о типе или члене, необходимо использовать файл документации вместе с отражением на текущий тип или член.</span><span class="sxs-lookup"><span data-stu-id="e3a0c-178">To get full information about a type or member, the documentation file must be used together with reflection on the actual type or member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3a0c-179">См. также</span><span class="sxs-lookup"><span data-stu-id="e3a0c-179">See Also</span></span>  
 <span data-ttu-id="e3a0c-180">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e3a0c-180">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e3a0c-181">[/doc (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="e3a0c-181">[/doc (C# Compiler Options)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) </span></span>  
 [<span data-ttu-id="e3a0c-182">Комментарии XML-документации</span><span class="sxs-lookup"><span data-stu-id="e3a0c-182">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)

