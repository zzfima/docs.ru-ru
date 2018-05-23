---
title: Практическое руководство. Использование XML-документации (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
ms.openlocfilehash: 6c7e30d23868959145e8941057f1c633fe6e374e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-the-xml-documentation-features-c-programming-guide"></a><span data-ttu-id="11129-102">Практическое руководство. Использование XML-документации (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="11129-102">How to: Use the XML Documentation Features (C# Programming Guide)</span></span>
<span data-ttu-id="11129-103">В данном примере представлены основные общие сведения о задокументированном типе.</span><span class="sxs-lookup"><span data-stu-id="11129-103">The following sample provides a basic overview of a type that has been documented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11129-104">Пример</span><span class="sxs-lookup"><span data-stu-id="11129-104">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]  
  
 <span data-ttu-id="11129-105">**// Этот XML-файл был создан в предыдущем образце кода.**</span><span class="sxs-lookup"><span data-stu-id="11129-105">**// This .xml file was generated with the previous code sample.**</span></span>  
<span data-ttu-id="11129-106">**\<?xml version="1.0"?>**</span><span class="sxs-lookup"><span data-stu-id="11129-106">**\<?xml version="1.0"?>**</span></span>  
<span data-ttu-id="11129-107">**\<doc>**</span><span class="sxs-lookup"><span data-stu-id="11129-107">**\<doc>**</span></span>  
 <span data-ttu-id="11129-108">**\<assembly>**</span><span class="sxs-lookup"><span data-stu-id="11129-108">**\<assembly>**</span></span>  
 <span data-ttu-id="11129-109">**\<name>xmlsample\</name>**</span><span class="sxs-lookup"><span data-stu-id="11129-109">**\<name>xmlsample\</name>**</span></span>  
 <span data-ttu-id="11129-110">**\</assembly>**</span><span class="sxs-lookup"><span data-stu-id="11129-110">**\</assembly>**</span></span>  
 <span data-ttu-id="11129-111">**\<members>**</span><span class="sxs-lookup"><span data-stu-id="11129-111">**\<members>**</span></span>  
 <span data-ttu-id="11129-112">**\<member name="T:SomeClass">**</span><span class="sxs-lookup"><span data-stu-id="11129-112">**\<member name="T:SomeClass">**</span></span>  
 <span data-ttu-id="11129-113">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="11129-113">**\<summary>**</span></span>  
 <span data-ttu-id="11129-114">**Здесь сводная документация об уровне класса.\</summary>**</span><span class="sxs-lookup"><span data-stu-id="11129-114">**Class level summary documentation goes here.\</summary>**</span></span>  
 <span data-ttu-id="11129-115">**\<remarks>**</span><span class="sxs-lookup"><span data-stu-id="11129-115">**\<remarks>**</span></span>  
 <span data-ttu-id="11129-116">**Расширенные комментарии можно связать с типом или членом**</span><span class="sxs-lookup"><span data-stu-id="11129-116">**Longer comments can be associated with a type or member**</span></span>  
 <span data-ttu-id="11129-117">**при помощи тега remarks\</remarks>**</span><span class="sxs-lookup"><span data-stu-id="11129-117">**through the remarks tag\</remarks>**</span></span>  
 <span data-ttu-id="11129-118">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="11129-118">**\</member>**</span></span>  
 <span data-ttu-id="11129-119">**\<member name="F:SomeClass.m_Name">**</span><span class="sxs-lookup"><span data-stu-id="11129-119">**\<member name="F:SomeClass.m_Name">**</span></span>  
 <span data-ttu-id="11129-120">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="11129-120">**\<summary>**</span></span>  
 <span data-ttu-id="11129-121">**Хранилище для свойства name\</summary>**</span><span class="sxs-lookup"><span data-stu-id="11129-121">**Store for the name property\</summary>**</span></span>  
 <span data-ttu-id="11129-122">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="11129-122">**\</member>**</span></span>  
 <span data-ttu-id="11129-123">**\<member name="M:SomeClass.#ctor">**</span><span class="sxs-lookup"><span data-stu-id="11129-123">**\<member name="M:SomeClass.#ctor">**</span></span>  
 <span data-ttu-id="11129-124">**\<summary>Конструктор класса.\</summary>**</span><span class="sxs-lookup"><span data-stu-id="11129-124">**\<summary>The class constructor.\</summary>**</span></span>  
 <span data-ttu-id="11129-125">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="11129-125">**\</member>**</span></span>  
 <span data-ttu-id="11129-126">**\<member name="M:SomeClass.SomeMethod(System.String)">**</span><span class="sxs-lookup"><span data-stu-id="11129-126">**\<member name="M:SomeClass.SomeMethod(System.String)">**</span></span>  
 <span data-ttu-id="11129-127">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="11129-127">**\<summary>**</span></span>  
 <span data-ttu-id="11129-128">**Описание метода SomeMethod.\</summary>**</span><span class="sxs-lookup"><span data-stu-id="11129-128">**Description for SomeMethod.\</summary>**</span></span>  
 <span data-ttu-id="11129-129">**\<param name="s"> Здесь описание параметра s\</param>**</span><span class="sxs-lookup"><span data-stu-id="11129-129">**\<param name="s"> Parameter description for s goes here\</param>**</span></span>  
 <span data-ttu-id="11129-130">**\<seealso cref="T:System.String">**</span><span class="sxs-lookup"><span data-stu-id="11129-130">**\<seealso cref="T:System.String">**</span></span>  
 <span data-ttu-id="11129-131">**Атрибут cref можно использовать в любом теге для ссылки на тип или член**</span><span class="sxs-lookup"><span data-stu-id="11129-131">**You can use the cref attribute on any tag to reference a type or member**</span></span>  
 <span data-ttu-id="11129-132">**и тогда компилятор проверит существование ссылки. \</seealso>**</span><span class="sxs-lookup"><span data-stu-id="11129-132">**and the compiler will check that the reference exists. \</seealso>**</span></span>  
 <span data-ttu-id="11129-133">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="11129-133">**\</member>**</span></span>  
 <span data-ttu-id="11129-134">**\<member name="M:SomeClass.SomeOtherMethod">**</span><span class="sxs-lookup"><span data-stu-id="11129-134">**\<member name="M:SomeClass.SomeOtherMethod">**</span></span>  
 <span data-ttu-id="11129-135">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="11129-135">**\<summary>**</span></span>  
 <span data-ttu-id="11129-136">**Какой-либо другой метод. \</summary>**</span><span class="sxs-lookup"><span data-stu-id="11129-136">**Some other method. \</summary>**</span></span>  
 <span data-ttu-id="11129-137">**\<returns>**</span><span class="sxs-lookup"><span data-stu-id="11129-137">**\<returns>**</span></span>  
 <span data-ttu-id="11129-138">**Возврат результатов, описанных при помощи тега returns.\</returns>**</span><span class="sxs-lookup"><span data-stu-id="11129-138">**Return results are described through the returns tag.\</returns>**</span></span>  
 <span data-ttu-id="11129-139">**\<seealso cref="M:SomeClass.SomeMethod(System.String)">**</span><span class="sxs-lookup"><span data-stu-id="11129-139">**\<seealso cref="M:SomeClass.SomeMethod(System.String)">**</span></span>  
 <span data-ttu-id="11129-140">**Обратите внимание, что атрибут cref используется для ссылки на указанный метод \</seealso>**</span><span class="sxs-lookup"><span data-stu-id="11129-140">**Notice the use of the cref attribute to reference a specific method \</seealso>**</span></span>  
 <span data-ttu-id="11129-141">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="11129-141">**\</member>**</span></span>  
 <span data-ttu-id="11129-142">**\<member name="M:SomeClass.Main(System.String[])">**</span><span class="sxs-lookup"><span data-stu-id="11129-142">**\<member name="M:SomeClass.Main(System.String[])">**</span></span>  
 <span data-ttu-id="11129-143">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="11129-143">**\<summary>**</span></span>  
 <span data-ttu-id="11129-144">**Точка входа для приложения.**</span><span class="sxs-lookup"><span data-stu-id="11129-144">**The entry point for the application.**</span></span>  
 <span data-ttu-id="11129-145">**\</summary>**</span><span class="sxs-lookup"><span data-stu-id="11129-145">**\</summary>**</span></span>  
 <span data-ttu-id="11129-146">**\<param name="args"> Список аргументов командной строки\</param>**</span><span class="sxs-lookup"><span data-stu-id="11129-146">**\<param name="args"> A list of command line arguments\</param>**</span></span>  
 <span data-ttu-id="11129-147">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="11129-147">**\</member>**</span></span>  
 <span data-ttu-id="11129-148">**\<member name="P:SomeClass.Name">**</span><span class="sxs-lookup"><span data-stu-id="11129-148">**\<member name="P:SomeClass.Name">**</span></span>  
 <span data-ttu-id="11129-149">**\<summary>**</span><span class="sxs-lookup"><span data-stu-id="11129-149">**\<summary>**</span></span>  
 <span data-ttu-id="11129-150">**Свойство Name \</summary>**</span><span class="sxs-lookup"><span data-stu-id="11129-150">**Name property \</summary>**</span></span>  
 <span data-ttu-id="11129-151">**\<value>**</span><span class="sxs-lookup"><span data-stu-id="11129-151">**\<value>**</span></span>  
 <span data-ttu-id="11129-152">**Тег value используется для описания значения свойства\</value>**</span><span class="sxs-lookup"><span data-stu-id="11129-152">**A value tag is used to describe the property value\</value>**</span></span>  
 <span data-ttu-id="11129-153">**\</member>**</span><span class="sxs-lookup"><span data-stu-id="11129-153">**\</member>**</span></span>  
 <span data-ttu-id="11129-154">**\</members>**</span><span class="sxs-lookup"><span data-stu-id="11129-154">**\</members>**</span></span>  
<span data-ttu-id="11129-155">**\</doc>**</span><span class="sxs-lookup"><span data-stu-id="11129-155">**\</doc>**</span></span>   
## <a name="compiling-the-code"></a><span data-ttu-id="11129-156">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="11129-156">Compiling the Code</span></span>  
 <span data-ttu-id="11129-157">Чтобы скомпилировать этот пример, введите в командной строке:</span><span class="sxs-lookup"><span data-stu-id="11129-157">To compile the example, type the following command line:</span></span>  
  
 `csc XMLsample.cs /doc:XMLsample.xml`  
  
 <span data-ttu-id="11129-158">Эта команда создает XML-файл XMLsample.xml, который можно просмотреть в браузере или с помощью команды TYPE.</span><span class="sxs-lookup"><span data-stu-id="11129-158">This will create the XML file XMLsample.xml, which you can view in your browser or by using the TYPE command.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="11129-159">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="11129-159">Robust Programming</span></span>  
 <span data-ttu-id="11129-160">Документация XML начинается с ///.</span><span class="sxs-lookup"><span data-stu-id="11129-160">XML documentation starts with ///.</span></span> <span data-ttu-id="11129-161">При создании нового проекта мастер добавляет несколько строк ///.</span><span class="sxs-lookup"><span data-stu-id="11129-161">When you create a new project, the wizards put some starter /// lines in for you.</span></span> <span data-ttu-id="11129-162">Обработка этих комментариев имеет некоторые ограничения.</span><span class="sxs-lookup"><span data-stu-id="11129-162">The processing of these comments has some restrictions:</span></span>  
  
-   <span data-ttu-id="11129-163">Документация должна представлять собой XML с правильным форматом.</span><span class="sxs-lookup"><span data-stu-id="11129-163">The documentation must be well-formed XML.</span></span> <span data-ttu-id="11129-164">Если формат XML неверен, то выдается предупреждение и файл документации содержит комментарий о том, что произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="11129-164">If the XML is not well-formed, a warning is generated and the documentation file will contain a comment that says that an error was encountered.</span></span>  
  
-   <span data-ttu-id="11129-165">Разработчики могут создавать собственные наборы тегов.</span><span class="sxs-lookup"><span data-stu-id="11129-165">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="11129-166">Однако существует рекомендуемый набор тегов (см. раздел "См. также" в данной теме).</span><span class="sxs-lookup"><span data-stu-id="11129-166">There is a recommended set of tags (see the Further Reading section).</span></span> <span data-ttu-id="11129-167">Некоторые рекомендуемые теги имеют особые значения.</span><span class="sxs-lookup"><span data-stu-id="11129-167">Some of the recommended tags have special meanings:</span></span>  
  
    -   <span data-ttu-id="11129-168">Тег \<param> используется для описания параметров.</span><span class="sxs-lookup"><span data-stu-id="11129-168">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="11129-169">При использовании этого тега компилятор проверяет, что параметр существует и все параметры описаны в документации.</span><span class="sxs-lookup"><span data-stu-id="11129-169">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="11129-170">При сбое проверки компилятор выдает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="11129-170">If the verification failed, the compiler issues a warning.</span></span>  
  
    -   <span data-ttu-id="11129-171">Атрибут `cref` может быть присоединен к любому тегу для предоставления ссылки на элемент кода.</span><span class="sxs-lookup"><span data-stu-id="11129-171">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="11129-172">Компилятор проверяет наличие этого элемента кода.</span><span class="sxs-lookup"><span data-stu-id="11129-172">The compiler will verify that this code element exists.</span></span> <span data-ttu-id="11129-173">При сбое проверки компилятор выдает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="11129-173">If the verification failed, the compiler issues a warning.</span></span> <span data-ttu-id="11129-174">Компилятор учитывает любые операторы `using` при поиске типа, описанного в атрибуте `cref`.</span><span class="sxs-lookup"><span data-stu-id="11129-174">The compiler respects any `using` statements when it looks for a type described in the `cref` attribute.</span></span>  
  
    -   <span data-ttu-id="11129-175">Тег \<summary> используется технологией IntelliSense в Visual Studio для отображения дополнительных сведений о типе или члене.</span><span class="sxs-lookup"><span data-stu-id="11129-175">The \<summary> tag is used by IntelliSense inside Visual Studio to display additional information about a type or member.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="11129-176">XML-файл не предоставляет полную информацию о типе и членах (например, он не содержит никаких сведений о типе).</span><span class="sxs-lookup"><span data-stu-id="11129-176">The XML file does not provide full information about the type and members (for example, it does not contain any type information).</span></span> <span data-ttu-id="11129-177">Чтобы получить полную информацию о типе или члене, необходимо использовать файл документации вместе с отражением на текущий тип или член.</span><span class="sxs-lookup"><span data-stu-id="11129-177">To get full information about a type or member, the documentation file must be used together with reflection on the actual type or member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11129-178">См. также</span><span class="sxs-lookup"><span data-stu-id="11129-178">See Also</span></span>  
 [<span data-ttu-id="11129-179">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="11129-179">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="11129-180">/doc (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="11129-180">/doc (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
 [<span data-ttu-id="11129-181">Комментарии XML-документации</span><span class="sxs-lookup"><span data-stu-id="11129-181">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)
