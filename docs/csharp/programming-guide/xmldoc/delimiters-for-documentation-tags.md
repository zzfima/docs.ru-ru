---
title: Руководство по программированию на C#. Разделители для тегов в документации
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- XML [C#], delimiters
- /** */ delimiters for C# documentation tags
- /// delimiter for C# documentation
ms.assetid: 9b2bdd18-4f5c-4c0b-988e-fb992e0d233e
ms.openlocfilehash: 17594e557df922c1c512b4d643cd85ac76ea5a81
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523493"
---
# <a name="delimiters-for-documentation-tags-c-programming-guide"></a><span data-ttu-id="b426a-102">Разделители для тегов в документации (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="b426a-102">Delimiters for Documentation Tags (C# Programming Guide)</span></span>
<span data-ttu-id="b426a-103">Для создания комментариев в документах XML необходимо использовать разделители, по которым компилятор определяет начало и конец комментария.</span><span class="sxs-lookup"><span data-stu-id="b426a-103">The use of XML doc comments requires delimiters, which indicate to the compiler where a documentation comment begins and ends.</span></span> <span data-ttu-id="b426a-104">С тегами в XML-документации можно использовать следующие виды разделителей:</span><span class="sxs-lookup"><span data-stu-id="b426a-104">You can use the following kinds of delimiters with the XML documentation tags:</span></span>  
  
 `///`  
 <span data-ttu-id="b426a-105">Однострочный разделитель.</span><span class="sxs-lookup"><span data-stu-id="b426a-105">Single-line delimiter.</span></span> <span data-ttu-id="b426a-106">Это форма, представленная в примерах документов и используемая в шаблонах проектов Visual C#.</span><span class="sxs-lookup"><span data-stu-id="b426a-106">This is the form that is shown in documentation examples and used by the Visual C# project templates.</span></span> <span data-ttu-id="b426a-107">Если после разделителя имеется символ пробела, этот символ не включается в выходные данные XML.</span><span class="sxs-lookup"><span data-stu-id="b426a-107">If there is a white space character following the delimiter, that character is not included in the XML output.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b426a-108">В интегрированной среде разработки Visual Studio имеется функция автоматического редактирования комментариев Smart Comment Editing, которая автоматически вставляет теги \<summary> и \</summary> и перемещает курсор в этих тегах после ввода разделителя `///` в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="b426a-108">The Visual Studio IDE has a feature called Smart Comment Editing that automatically inserts the \<summary> and \</summary> tags and moves your cursor within these tags after you type the `///` delimiter in the Code Editor.</span></span> <span data-ttu-id="b426a-109">Вы можете включить или отключить эту функцию в [диалоговом окне "Параметры"](/visualstudio/ide/reference/options-text-editor-csharp-advanced).</span><span class="sxs-lookup"><span data-stu-id="b426a-109">You can turn this feature on or off in the [Options dialog box](/visualstudio/ide/reference/options-text-editor-csharp-advanced).</span></span>  
  
 `/** */`  
 <span data-ttu-id="b426a-110">Многострочные разделители.</span><span class="sxs-lookup"><span data-stu-id="b426a-110">Multiline delimiters.</span></span>  
  
 <span data-ttu-id="b426a-111">При использовании разделителей `/** */` нужно следовать нескольким правилам форматирования.</span><span class="sxs-lookup"><span data-stu-id="b426a-111">There are some formatting rules to follow when you use the `/** */` delimiters.</span></span>  
  
- <span data-ttu-id="b426a-112">Строка, содержащая разделитель `/**`, не обрабатывается как комментарий, если оставшаяся ее часть представляет собой пробелы.</span><span class="sxs-lookup"><span data-stu-id="b426a-112">On the line that contains the `/**` delimiter, if the remainder of the line is white space, the line is not processed for comments.</span></span> <span data-ttu-id="b426a-113">Если первый знак после разделителя `/**` является пробелом, то этот пробел игнорируется, а оставшаяся часть строки обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="b426a-113">If the first character after the `/**` delimiter is white space, that white space character is ignored and the rest of the line is processed.</span></span> <span data-ttu-id="b426a-114">В противном случае весь текст, расположенный в строке после разделителя `/**`, обрабатывается как часть комментария.</span><span class="sxs-lookup"><span data-stu-id="b426a-114">Otherwise, the entire text of the line after the `/**` delimiter is processed as part of the comment.</span></span>  
  
- <span data-ttu-id="b426a-115">Строка, содержащая разделитель `*/`, игнорируется, если перед разделителем `*/` стоят только пробелы.</span><span class="sxs-lookup"><span data-stu-id="b426a-115">On the line that contains the `*/` delimiter, if there is only white space up to the `*/` delimiter, that line is ignored.</span></span> <span data-ttu-id="b426a-116">В противном случае текст строки, расположенный перед разделителем `*/`, обрабатывается как часть комментария, и к нему применяются правила сопоставления шаблонов, описанные в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="b426a-116">Otherwise, the text on the line up to the `*/` delimiter is processed as part of the comment, subject to the pattern-matching rules described in the following bullet.</span></span>  
  
- <span data-ttu-id="b426a-117">В начале каждой из строк, расположенных после строки, которая начинается с разделителя `/**`, компилятор выполняет поиск общего шаблона.</span><span class="sxs-lookup"><span data-stu-id="b426a-117">For the lines after the one that begins with the `/**` delimiter, the compiler looks for a common pattern at the beginning of each line.</span></span> <span data-ttu-id="b426a-118">Шаблон может включать необязательный пробел и знак звездочки (`*`), после которого следуют необязательные пробелы.</span><span class="sxs-lookup"><span data-stu-id="b426a-118">The pattern can consist of optional white space and an asterisk (`*`), followed by more optional white space.</span></span> <span data-ttu-id="b426a-119">Если компилятор находит общий шаблон в начале каждой строки, которая не начинается с разделителя `/**` или `*/`, он игнорирует этот шаблон для каждой строки.</span><span class="sxs-lookup"><span data-stu-id="b426a-119">If the compiler finds a common pattern at the beginning of each line that does not begin with the `/**` delimiter or the `*/` delimiter, it ignores that pattern for each line.</span></span>  
  
 <span data-ttu-id="b426a-120">Эти правила показаны в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="b426a-120">The following examples illustrate these rules.</span></span>  
  
- <span data-ttu-id="b426a-121">В следующем комментарии будет обработана только строка, которая начинается с `<summary>`.</span><span class="sxs-lookup"><span data-stu-id="b426a-121">The only part of the following comment that will be processed is the line that begins with `<summary>`.</span></span> <span data-ttu-id="b426a-122">Формат с тремя тегами позволяет создать точно такие же комментарии.</span><span class="sxs-lookup"><span data-stu-id="b426a-122">The three tag formats produce the same comments.</span></span>  
  
    ```csharp  
    /** <summary>text</summary> */   
  
    /**   
    <summary>text</summary>   
    */   
  
    /**   
     * <summary>text</summary>   
    */  
    ```  
  
- <span data-ttu-id="b426a-123">Компилятор обнаруживает в начале второй и третьей строки общий шаблон " \* ".</span><span class="sxs-lookup"><span data-stu-id="b426a-123">The compiler identifies a common pattern of " \* " at the beginning of the second and third lines.</span></span> <span data-ttu-id="b426a-124">Шаблон не включается в выходные данные.</span><span class="sxs-lookup"><span data-stu-id="b426a-124">The pattern is not included in the output.</span></span>  
  
    ```csharp  
    /**   
     * <summary>   
     * text </summary>*/   
    ```  
  
- <span data-ttu-id="b426a-125">Компилятор не обнаруживает общий шаблон в следующем комментарии, так как второй знак в третьей строке не является звездочкой.</span><span class="sxs-lookup"><span data-stu-id="b426a-125">The compiler finds no common pattern in the following comment because the second character on the third line is not an asterisk.</span></span> <span data-ttu-id="b426a-126">Следовательно, весь текст во второй и третьей строках обрабатывается как часть примечания.</span><span class="sxs-lookup"><span data-stu-id="b426a-126">Therefore, all text on the second and third lines is processed as part of the comment.</span></span>  
  
    ```csharp  
    /**   
     * <summary>   
       text </summary>  
    */   
    ```  
  
- <span data-ttu-id="b426a-127">Компилятор не обнаруживает шаблон в следующем комментарии по двум причинам.</span><span class="sxs-lookup"><span data-stu-id="b426a-127">The compiler finds no pattern in the following comment for two reasons.</span></span> <span data-ttu-id="b426a-128">Во-первых, количество пробелов перед звездочкой не согласовано.</span><span class="sxs-lookup"><span data-stu-id="b426a-128">First, the number of spaces before the asterisk is not consistent.</span></span> <span data-ttu-id="b426a-129">Во-вторых, пятая строка начинается с символа табуляции, который отличается от пробелов.</span><span class="sxs-lookup"><span data-stu-id="b426a-129">Second, the fifth line begins with a tab, which does not match spaces.</span></span> <span data-ttu-id="b426a-130">Таким образом, весь текст из строк со второй по пятую обрабатывается как часть комментария.</span><span class="sxs-lookup"><span data-stu-id="b426a-130">Therefore, all text from lines two through five is processed as part of the comment.</span></span>  
  
    ```csharp  
    /**   
      * <summary>   
      * text   
     *  text2   
        *  </summary>   
    */   
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b426a-131">См. также</span><span class="sxs-lookup"><span data-stu-id="b426a-131">See also</span></span>

- [<span data-ttu-id="b426a-132">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="b426a-132">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b426a-133">Комментарии XML-документации</span><span class="sxs-lookup"><span data-stu-id="b426a-133">XML Documentation Comments</span></span>](./index.md)
- [<span data-ttu-id="b426a-134">-doc (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="b426a-134">-doc (C# Compiler Options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="b426a-135">Комментарии XML-документации</span><span class="sxs-lookup"><span data-stu-id="b426a-135">XML Documentation Comments</span></span>](./index.md)
