---
title: Выполнение в коллекциях строковых операций, не зависящих от языка и региональных параметров
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CaseInsensitiveComparer class, using
- CollectionsUtil.CreateCaseInsensitiveHashtable method
- culture-insensitive string operations, collections
- collections [.NET Framework], culture-insensitive string operations
- CaseInsensitiveHashCodeProvider class, using
- ArrayList.Sort method
- SortedList class, culture-insensitive string operations
- culture parameter
ms.assetid: 5cdc9396-a64b-4615-a1cd-b605db4c5983
ms.openlocfilehash: 5bd6e49f23ca5b694664393f3eb18cc72ada7bdd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120820"
---
# <a name="performing-culture-insensitive-string-operations-in-collections"></a>Выполнение в коллекциях строковых операций, не зависящих от языка и региональных параметров

В пространстве имен <xref:System.Collections> существуют классы и члены, поведение которых по умолчанию зависит от языка и региональных параметров. Конструкторы без параметров для классов <xref:System.Collections.CaseInsensitiveComparer> и <xref:System.Collections.CaseInsensitiveHashCodeProvider> инициализируют новый экземпляр с помощью свойства <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType>. Все перегрузки метода <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> создают новый экземпляр класса <xref:System.Collections.Hashtable>, по умолчанию используя свойство `Thread.CurrentCulture`. Перегруженные версии метода <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> по умолчанию выполняют сортировку с учетом языка и региональных параметров, используя свойства `Thread.CurrentCulture`. Если в качестве ключей используются строки, на сортировку и поиск по <xref:System.Collections.SortedList> влияет значение `Thread.CurrentCulture`. Для получения результатов, не зависящих от языка и региональных параметров, для этих классов и методов в пространстве имен `Collections` следуйте рекомендациям, приведенным в этом разделе.

> [!NOTE]
> Если передать <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> в метод сравнения, сравнение выполняется без учета языка и региональных параметров. Однако при этом не выполняется нелингвистическое сравнение, например для путей к файлам, разделов реестра и переменных среды. Также не поддерживается принятие решений по безопасности на основе результата сравнения. Для нелингвистического сравнения и (или) поддержки принятия решений по безопасности в приложении следует использовать метод сравнения, который принимает значение <xref:System.StringComparison>. Приложение должно передавать <xref:System.StringComparison>.

## <a name="using-the-caseinsensitivecomparer-and-caseinsensitivehashcodeprovider-classes"></a>Использование классов CaseInsensitiveComparer и CaseInsensitiveHashCodeProvider

В конструкторах без параметров для `CaseInsensitiveHashCodeProvider` и `CaseInsensitiveComparer` инициализируется новый экземпляр класса с использованием `Thread.CurrentCulture`. Это приводит к тому, что язык и региональные параметры учитываются при сравнении. В следующем примере кода показан конструктор для `Hashtable`, который учитывает язык и региональные параметры, так как он использует конструкторы без параметров для `CaseInsensitiveHashCodeProvider` и `CaseInsensitiveComparer`.

```vb
internalHashtable = New Hashtable(CaseInsensitiveHashCodeProvider.Default, CaseInsensitiveComparer.Default)
```

```csharp
internalHashtable = new Hashtable(CaseInsensitiveHashCodeProvider.Default, CaseInsensitiveComparer.Default);
```

Если вы хотите создать `Hashtable`, не учитывающий язык и региональные параметры, с помощью классов `CaseInsensitiveComparer` и `CaseInsensitiveHashCodeProvider`, инициализируйте новые экземпляры этих классов с помощью конструкторов, которые принимают параметр `culture`. В качестве параметра `culture` укажите <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. В следующем примере кода показан конструктор для `Hashtable`, который не учитывает язык и региональные параметры.

```vb
internalHashtable = New Hashtable(New
    CaseInsensitiveHashCodeProvider(CultureInfo.InvariantCulture),
    New CaseInsensitiveComparer(CultureInfo.InvariantCulture))
```

```csharp
internalHashtable = new Hashtable(new CaseInsensitiveHashCodeProvider
    (CultureInfo.InvariantCulture),
    new CaseInsensitiveComparer(CultureInfo.InvariantCulture));
```

## <a name="using-the-collectionsutilcreatecaseinsensitivehashtable-method"></a>Использование метода CollectionsUtil.CreateCaseInsensitiveHashTable

Для создания нового экземпляра класса `Hashtable`, который не учитывает регистр строк, удобно использовать метод `CollectionsUtil.CreateCaseInsensitiveHashTable`. Однако все перегруженные версии метода `CollectionsUtil.CreateCaseInsensitiveHashTable` учитывают язык и региональные параметры, так как они используют свойство `Thread.CurrentCulture`. С помощью этого метода нельзя создать `Hashtable`, который не учитывает язык и региональные параметры. Чтобы создать `Hashtable`, который не учитывает язык и региональные параметры, используйте конструктор `Hashtable`, который принимает параметр `culture`. В качестве параметра `culture` укажите `CultureInfo.InvariantCulture`. В следующем примере кода показан конструктор для `Hashtable`, который не учитывает язык и региональные параметры.

```vb
internalHashtable = New Hashtable(New
    CaseInsensitiveHashCodeProvider(CultureInfo.InvariantCulture),
    New CaseInsensitiveComparer(CultureInfo.InvariantCulture))
```

```csharp
internalHashtable = new Hashtable(new CaseInsensitiveHashCodeProvider
    (CultureInfo.InvariantCulture),
    new CaseInsensitiveComparer(CultureInfo.InvariantCulture));
```

<a name="cpconperformingculture-insensitivestringoperationsincollectionsanchor1"></a>

## <a name="using-the-sortedlist-class"></a>Использование класса SortedList

`SortedList` представляет коллекцию пар "ключ — значение", упорядоченных по ключу. Обращаться к парам можно по ключу и индексу. Если используется `SortedList` и в качестве ключей используются строки, на поиск и сортировку может повлиять свойство `Thread.CurrentCulture`. Чтобы `SortedList` не учитывал язык и региональные параметры, создайте `SortedList` с помощью одного из конструкторов, принимающих параметр `comparer`. Параметр `comparer` указывает реализацию <xref:System.Collections.IComparer>, которую нужно использовать при сравнении ключей. Для сравнения ключей в качестве параметра укажите пользовательский класс сравнения, который использует `CultureInfo.InvariantCulture`. В следующем примере показан пользовательский класс сравнения, не учитывающий язык и региональные параметры. Для этого в конструктор `SortedList` передается параметр `comparer`.

```vb
Imports System
Imports System.Collections
Imports System.Globalization

Friend Class InvariantComparer
    Implements IComparer
    Private m_compareInfo As CompareInfo
    Friend Shared [Default] As New InvariantComparer()

    Friend Sub New()
        m_compareInfo = CultureInfo.InvariantCulture.CompareInfo
    End Sub

    Public Function Compare(a As Object, b As Object) As Integer _
            Implements IComparer.Compare
        Dim sa As String = CType(a, String)
        Dim sb As String = CType(b, String)
        If Not (sa Is Nothing) And Not (sb Is Nothing) Then
            Return m_compareInfo.Compare(sa, sb)
        Else
            Return Comparer.Default.Compare(a, b)
        End If
    End Function
End Class
```

```csharp
using System;
using System.Collections;
using System.Globalization;

internal class InvariantComparer : IComparer
{
    private CompareInfo m_compareInfo;
    internal static readonly InvariantComparer Default = new
        InvariantComparer();

    internal InvariantComparer()
    {
        m_compareInfo = CultureInfo.InvariantCulture.CompareInfo;
    }

    public int Compare(Object a, Object b)
    {
        String sa = a as String;
        String sb = b as String;
        if (sa != null && sb != null)
            return m_compareInfo.Compare(sa, sb);
        else
            return Comparer.Default.Compare(a,b);
    }
}
```

В общем случае при использовании `SortedList` для строк без указания пользовательского инвариантного класса сравнения изменение `Thread.CurrentCulture` после заполнения списка может сделать список недействительным.

## <a name="using-the-arraylistsort-method"></a>Использование метода ArrayList.Sort

Перегруженные версии метода по умолчанию `ArrayList.Sort` выполняют сортировку с учетом языка и региональных параметров благодаря использованию свойства `Thread.CurrentCulture`. Результаты могут различаться из-за различного порядка сортировки в разных языках и региональных параметрах. Чтобы результат не зависел от языка и региональных параметров, используйте перегрузки этого метода, которые принимают реализацию `IComparer`. В качестве параметра `comparer` укажите пользовательский инвариантный класс сравнения, который использует `CultureInfo.InvariantCulture`. Пример пользовательского инвариантного класса сравнения приведен в разделе [Использование класса SortedList](#cpconperformingculture-insensitivestringoperationsincollectionsanchor1).

## <a name="see-also"></a>См. также

- <xref:System.Collections.CaseInsensitiveComparer>
- <xref:System.Collections.CaseInsensitiveHashCodeProvider>
- <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType>
- <xref:System.Collections.SortedList>
- <xref:System.Collections.Hashtable>
- <xref:System.Collections.IComparer>
- [Выполнение строковых операций, не зависящих от языка и региональных параметров](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
- <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType>
