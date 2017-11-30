---
title: "Класс Exception и его свойства"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exceptions, Exception class
- Exception class
ms.assetid: e2e1f8c4-e7b4-467d-9a66-13c90861221d
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 253a9846e484aa4e54c3433b0bbc8623519bbb7e
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2017
---
# <a name="exception-class-and-properties"></a><span data-ttu-id="91bc5-102">Класс и свойства исключений</span><span class="sxs-lookup"><span data-stu-id="91bc5-102">Exception class and properties</span></span>

<span data-ttu-id="91bc5-103"><xref:System.Exception> — это базовый класс, от которого наследуются исключения.</span><span class="sxs-lookup"><span data-stu-id="91bc5-103">The <xref:System.Exception> class is the base class from which exceptions inherit.</span></span> <span data-ttu-id="91bc5-104">Например, иерархия класса <xref:System.InvalidCastException> имеет следующий вид:</span><span class="sxs-lookup"><span data-stu-id="91bc5-104">For example, the <xref:System.InvalidCastException> class hierarchy is as follows:</span></span>

```
Object
  Exception
    SystemException
       InvalidCastException
```

<span data-ttu-id="91bc5-105">Класс <xref:System.Exception> имеет следующие свойства, которые облегчают анализ исключения.</span><span class="sxs-lookup"><span data-stu-id="91bc5-105">The <xref:System.Exception> class has the following properties that help make understanding an exception easier.</span></span>

| <span data-ttu-id="91bc5-106">Имя свойства</span><span class="sxs-lookup"><span data-stu-id="91bc5-106">Property Name</span></span> | <span data-ttu-id="91bc5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="91bc5-107">Description</span></span> |
| ------------- | ----------- |
| <xref:System.Exception.Data> | <span data-ttu-id="91bc5-108">Свойство <xref:System.Collections.IDictionary>, которое содержит произвольные данные в парах "ключ–значение".</span><span class="sxs-lookup"><span data-stu-id="91bc5-108">An <xref:System.Collections.IDictionary> that holds arbitrary data in key-value pairs.</span></span> |
| <xref:System.Exception.HelpLink> | <span data-ttu-id="91bc5-109">Может содержать URL-адрес (или URN) файла справки, который предоставляет подробные сведения о причине возникновения исключения.</span><span class="sxs-lookup"><span data-stu-id="91bc5-109">Can hold a URL (or URN) to a help file that provides extensive information about the cause of an exception.</span></span> |
| <xref:System.Exception.InnerException> | <span data-ttu-id="91bc5-110">Это свойство может использоваться для создания и сохранения последовательностей исключений во время обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="91bc5-110">This property can be used to create and preserve a series of exceptions during exception handling.</span></span> <span data-ttu-id="91bc5-111">Его можно использовать для создания нового исключения, содержащего ранее перехваченные исключения.</span><span class="sxs-lookup"><span data-stu-id="91bc5-111">You can use it to create a new exception that contains previously caught exceptions.</span></span> <span data-ttu-id="91bc5-112">Исходное исключение может быть перехвачено вторым исключением в свойстве <xref:System.Exception.InnerException>, что позволяет коду, обрабатывающему второе исключение, проверить дополнительные данные.</span><span class="sxs-lookup"><span data-stu-id="91bc5-112">The original exception can be captured by the second exception in the <xref:System.Exception.InnerException> property, allowing code that handles the second exception to examine the additional information.</span></span> <span data-ttu-id="91bc5-113">Например, предположим, что у вас есть метод, который принимает аргумент в неправильном формате.</span><span class="sxs-lookup"><span data-stu-id="91bc5-113">For example, suppose you have a method that receives an argument that's improperly formatted.</span></span>  <span data-ttu-id="91bc5-114">Код пытается считать аргумент, но создается исключение.</span><span class="sxs-lookup"><span data-stu-id="91bc5-114">The code tries to read the argument, but an exception is thrown.</span></span> <span data-ttu-id="91bc5-115">Метод перехватывает исключение и выдает <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="91bc5-115">The method catches the exception and throws a <xref:System.FormatException>.</span></span> <span data-ttu-id="91bc5-116">Чтобы расширить возможности вызывающего объекта для определения причины исключения, иногда желательно, чтобы метод перехватывал исключение, выданное вспомогательной процедурой, а затем выдавал исключение, содержащее больше сведений о возникшей ошибке.</span><span class="sxs-lookup"><span data-stu-id="91bc5-116">To improve the caller's ability to determine the reason an exception is thrown, it is sometimes desirable for a method to catch an exception thrown by a helper routine and then throw an exception more indicative of the error that has occurred.</span></span> <span data-ttu-id="91bc5-117">Можно создать новое и более информативное исключение, где ссылка на внутреннее исключение может указывать на исходное исключение.</span><span class="sxs-lookup"><span data-stu-id="91bc5-117">A new and more meaningful exception can be created, where the inner exception reference can be set to the original exception.</span></span> <span data-ttu-id="91bc5-118">Затем это более информативное исключение может выдаваться вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="91bc5-118">This more meaningful exception can then be thrown to the caller.</span></span> <span data-ttu-id="91bc5-119">Обратите внимание, что с помощью данной функции можно создать последовательность связанных исключений, которая завершается первым выданным исключением.</span><span class="sxs-lookup"><span data-stu-id="91bc5-119">Note that with this functionality, you can create a series of linked exceptions that ends with the exception that was thrown first.</span></span> |
| <xref:System.Exception.Message> | <span data-ttu-id="91bc5-120">Предоставляет сведения о причине возникновения исключения.</span><span class="sxs-lookup"><span data-stu-id="91bc5-120">Provides details about the cause of an exception.</span></span>
| <xref:System.Exception.Source> | <span data-ttu-id="91bc5-121">Возвращает или задает имя приложения или объекта, вызывавшего ошибку.</span><span class="sxs-lookup"><span data-stu-id="91bc5-121">Gets or sets the name of the application or the object that causes the error.</span></span> |
| <xref:System.Exception.StackTrace>| <span data-ttu-id="91bc5-122">Содержит трассировку стека, которую можно использовать для определения места возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="91bc5-122">Contains a stack trace that can be used to determine where an error occurred.</span></span> <span data-ttu-id="91bc5-123">Эта трассировка стека содержит имя исходного файла и, при наличии отладочной информации, номер программной строки.</span><span class="sxs-lookup"><span data-stu-id="91bc5-123">The stack trace includes the source file name and program line number if debugging information is available.</span></span> |

<span data-ttu-id="91bc5-124">Большинство классов, унаследованных от <xref:System.Exception>, не реализуют дополнительные элементы и не предоставляют дополнительные функции. Они просто наследуются от <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="91bc5-124">Most of the classes that inherit from <xref:System.Exception> do not implement additional members or provide additional functionality; they simply inherit from <xref:System.Exception>.</span></span> <span data-ttu-id="91bc5-125">Таким образом, наиболее важные сведения для исключения можно найти в иерархии классов исключений, имени исключения и информации, содержащейся в самом исключении.</span><span class="sxs-lookup"><span data-stu-id="91bc5-125">Therefore, the most important information for an exception can be found in the hierarchy of exception classes, the exception name, and the information contained in the exception.</span></span>

<span data-ttu-id="91bc5-126">Рекомендуется создавать и перехватывать только те объекты, которые являются производными от <xref:System.Exception>, но можно создавать любой объект, который является производным от <xref:System.Object> класса в список исключений.</span><span class="sxs-lookup"><span data-stu-id="91bc5-126">We recommend that you throw and catch only objects that derive from <xref:System.Exception>, but you can throw any object that derives from the <xref:System.Object> class as an exception.</span></span> <span data-ttu-id="91bc5-127">Обратите внимание, что не все языки поддерживают создание и перехват объектов, не являющихся производными от <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="91bc5-127">Note that not all languages support throwing and catching objects that do not derive from <xref:System.Exception>.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="91bc5-128">См. также</span><span class="sxs-lookup"><span data-stu-id="91bc5-128">See Also</span></span>  
[<span data-ttu-id="91bc5-129">Исключения</span><span class="sxs-lookup"><span data-stu-id="91bc5-129">Exceptions</span></span>](index.md)
