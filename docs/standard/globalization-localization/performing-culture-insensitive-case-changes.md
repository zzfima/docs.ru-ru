---
title: "Выполнение смены регистра независимо от языка и региональных параметров"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- String.ToLower method
- culture, case sensitivity
- Char.ToLower method
- case, changing in culture-insensitive strings
- Char.ToUpper method
- culture-insensitive string operations, case changes
- String.ToUpper method
- culture parameter
ms.assetid: 822d551c-c69a-4191-82f4-183d82c9179c
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c500b882c335572b8b458ba515b282e9f5362b85
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="performing-culture-insensitive-case-changes"></a><span data-ttu-id="96c8d-102">Выполнение смены регистра независимо от языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="96c8d-102">Performing Culture-Insensitive Case Changes</span></span>
<span data-ttu-id="96c8d-103"><xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, И <xref:System.Char.ToLower%2A?displayProperty=nameWithType> методы предоставляют перегрузки, которые не принимают параметры.</span><span class="sxs-lookup"><span data-stu-id="96c8d-103">The <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, and <xref:System.Char.ToLower%2A?displayProperty=nameWithType> methods provide overloads that do not accept any parameters.</span></span> <span data-ttu-id="96c8d-104">По умолчанию эти перегрузки без параметров выполняют изменения регистра, основанные на значении <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="96c8d-104">By default, these overloads without parameters perform case changes based on the value of the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="96c8d-105">Это приводит к результатам, с учетом регистра, которые может зависеть от языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="96c8d-105">This produces case-sensitive results that can vary by culture.</span></span> <span data-ttu-id="96c8d-106">Для того чтобы ясно показать изменение регистра для языка и региональных параметров с учетом или без учета языка и региональных параметров, следует использовать перегрузки этих методов, которые требуют явного задания `culture` параметра.</span><span class="sxs-lookup"><span data-stu-id="96c8d-106">To make it clear whether you want case changes to be culture-sensitive or culture-insensitive, you should use the overloads of these methods that require you to explicitly specify a `culture` parameter.</span></span> <span data-ttu-id="96c8d-107">Для изменения регистра с учетом языка и региональных параметров, укажите `CultureInfo.CurrentCulture` для `culture` параметра.</span><span class="sxs-lookup"><span data-stu-id="96c8d-107">For culture-sensitive case changes, specify `CultureInfo.CurrentCulture` for the `culture` parameter.</span></span> <span data-ttu-id="96c8d-108">Без учета языка и региональных параметров изменения регистра, укажите `CultureInfo.InvariantCulture` для `culture` параметра.</span><span class="sxs-lookup"><span data-stu-id="96c8d-108">For culture-insensitive case changes, specify `CultureInfo.InvariantCulture` for the `culture` parameter.</span></span>  
  
 <span data-ttu-id="96c8d-109">Часто строки преобразуются в стандартный обращение, чтобы включить упрощает поиск более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="96c8d-109">Often, strings are converted to a standard case to enable easier lookup later.</span></span> <span data-ttu-id="96c8d-110">При использовании строки таким образом, следует указать `CultureInfo.InvariantCulture` для `culture` параметра, так как значение <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> может измениться между моментом изменения регистра и время поиска.</span><span class="sxs-lookup"><span data-stu-id="96c8d-110">When strings are used in this way, you should specify `CultureInfo.InvariantCulture` for the `culture` parameter, because the value of <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> can potentially change between the time that the case is changed and the time that the lookup occurs.</span></span>  
  
 <span data-ttu-id="96c8d-111">Если решение безопасности зависит от операции изменения регистра, операции должно быть от языка и региональных параметров, чтобы гарантировать, что результат не повлияет значение `CultureInfo.CurrentCulture`.</span><span class="sxs-lookup"><span data-stu-id="96c8d-111">If a security decision is based on a case change operation, the operation should be culture-insensitive to ensure that the result is not affected by the value of `CultureInfo.CurrentCulture`.</span></span> <span data-ttu-id="96c8d-112">В разделе «Строка сравнения, текущего языка и региональных параметров» [советы и рекомендации по использованию строк](../../../docs/standard/base-types/best-practices-strings.md) статью для пример, демонстрирующий зависящие от языка и региональных параметров строковые операции может привести к непредсказуемым результатам.</span><span class="sxs-lookup"><span data-stu-id="96c8d-112">See the "String Comparisons that Use the Current Culture" section of the [Best Practices for Using Strings](../../../docs/standard/base-types/best-practices-strings.md) article for an example that demonstrates how culture-sensitive string operations can produce inconsistent results.</span></span>  
  
## <a name="using-the-stringtoupper-and-stringtolower-methods"></a><span data-ttu-id="96c8d-113">Используя String.ToUpper и String.ToLower методы</span><span class="sxs-lookup"><span data-stu-id="96c8d-113">Using the String.ToUpper and String.ToLower Methods</span></span>  
 <span data-ttu-id="96c8d-114">Для получения более понятного кода рекомендуется всегда использовать перегрузки `String.ToUpper` и `String.ToLower` методы, которые позволяют указать `culture` параметр явным образом.</span><span class="sxs-lookup"><span data-stu-id="96c8d-114">For code clarity, it is recommended that you always use overloads of the `String.ToUpper` and `String.ToLower` methods that allow you to specify a `culture` parameter explicitly.</span></span> <span data-ttu-id="96c8d-115">Например следующий код производит поиск идентификатора.</span><span class="sxs-lookup"><span data-stu-id="96c8d-115">For example, the following code performs an identifier lookup.</span></span> <span data-ttu-id="96c8d-116">`key.ToLower` Операция язык и региональные параметры по умолчанию, но это поведение не ясно из в коде.</span><span class="sxs-lookup"><span data-stu-id="96c8d-116">The `key.ToLower` operation is culture-sensitive by default, but this behavior is not clear from reading the code.</span></span>  
  
### <a name="example"></a><span data-ttu-id="96c8d-117">Пример</span><span class="sxs-lookup"><span data-stu-id="96c8d-117">Example</span></span>  
  
```vb  
Shared Function LookupKey(key As String) As Object  
   Return internalHashtable(key.ToLower())  
End Function  
```  
  
```csharp  
static object LookupKey(string key)   
{  
    return internalHashtable[key.ToLower()];  
}  
```  
  
 <span data-ttu-id="96c8d-118">Если вы хотите `key.ToLower` операции зависеть от языка и региональных параметров, следует изменить приведенный выше пример следующим образом, чтобы явно указать `CultureInfo.InvariantCulture` при изменении регистра.</span><span class="sxs-lookup"><span data-stu-id="96c8d-118">If you want the `key.ToLower` operation to be culture-insensitive, you should change the preceding example as follows to explicitly use the `CultureInfo.InvariantCulture` when changing the case.</span></span>  
  
```vb  
Shared Function LookupKey(key As String) As Object  
    Return internalHashtable(key.ToLower(CultureInfo.InvariantCulture))  
End Function  
```  
  
```csharp  
static object LookupKey(string key)   
{  
    return internalHashtable[key.ToLower(CultureInfo.InvariantCulture)];  
}  
```  
  
## <a name="using-the-chartoupper-and-chartolower-methods"></a><span data-ttu-id="96c8d-119">С помощью Char.ToUpper и Char.ToLower методов</span><span class="sxs-lookup"><span data-stu-id="96c8d-119">Using the Char.ToUpper and Char.ToLower Methods</span></span>  
 <span data-ttu-id="96c8d-120">Несмотря на то что `Char.ToUpper` и `Char.ToLower` методы имеют те же характеристики, что `String.ToUpper` и `String.ToLower` методы только языки и региональные параметры, которые подпадают под, турецкий (Турция) и Азербайджанский (латиница, Азербайджан).</span><span class="sxs-lookup"><span data-stu-id="96c8d-120">Although the `Char.ToUpper` and `Char.ToLower` methods have the same characteristics as the `String.ToUpper` and `String.ToLower` methods, the only cultures that are affected are Turkish (Turkey) and Azerbaijani (Latin, Azerbaijan).</span></span> <span data-ttu-id="96c8d-121">Это единственные языки и региональные параметры регистра одного символа отличается.</span><span class="sxs-lookup"><span data-stu-id="96c8d-121">These are the only two cultures with single-character casing differences.</span></span> <span data-ttu-id="96c8d-122">Дополнительные сведения об этом уникальном сопоставлении регистра см. в разделе "Регистр" описания класса <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="96c8d-122">For more details about this unique case mapping, see the "Casing" section in the <xref:System.String> class topic.</span></span> <span data-ttu-id="96c8d-123">Для получения более понятного кода и добиться согласованных результатов, рекомендуется всегда использовать перегрузки этих методов, которые позволяют явным образом указывать `culture` параметра.</span><span class="sxs-lookup"><span data-stu-id="96c8d-123">For code clarity and to ensure consistent results, it is recommended that you always use the overloads of these methods that allow you to explicitly specify a `culture` parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96c8d-124">См. также</span><span class="sxs-lookup"><span data-stu-id="96c8d-124">See Also</span></span>  
 <xref:System.String.ToUpper%2A?displayProperty=nameWithType>  
 <xref:System.String.ToLower%2A?displayProperty=nameWithType>  
 <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>  
 <xref:System.Char.ToLower%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="96c8d-125">Выполнение строковых операций, не зависящих от языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="96c8d-125">Performing Culture-Insensitive String Operations</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
