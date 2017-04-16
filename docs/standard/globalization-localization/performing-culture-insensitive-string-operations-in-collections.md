---
title: "Выполнение в коллекциях строковых операций, не зависящих от языка и региональных параметров | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ArrayList.Sort - метод"
  - "CaseInsensitiveComparer - класс, использование"
  - "CaseInsensitiveHashCodeProvider - класс, использование"
  - "коллекции [платформа .NET Framework], операции со строками без учета языка и региональных параметров"
  - "CollectionsUtil.CreateCaseInsensitiveHashtable - метод"
  - "языковый и региональный параметр"
  - "операции со строками без учета языка и региональных параметров, коллекции"
  - "SortedList - класс, операции со строками без учета языка и региональных параметров"
ms.assetid: 5cdc9396-a64b-4615-a1cd-b605db4c5983
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Выполнение в коллекциях строковых операций, не зависящих от языка и региональных параметров
В пространстве имен <xref:System.Collections> существуют классы и члены классов, поведение которых по умолчанию зависит от языка и региональных параметров.  Используемые по умолчанию конструкторы для классов <xref:System.Collections.CaseInsensitiveComparer> и <xref:System.Collections.CaseInsensitiveHashCodeProvider> инициализируют новый экземпляр с помощью свойства <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=fullName>.  Все перегруженные версии метода [CollectionsUtil.CreateCaseInsensitiveHashTable](frlrfSystemCollectionsSpecializedCollectionsUtilClassCreateCaseInsensitiveHashtableTopic) создают экземпляр класса <xref:System.Collections.Hashtable>, по умолчанию используя свойство `Thread.CurrentCulture`.  Перегруженные версии метода <xref:System.Collections.ArrayList.Sort%2A?displayProperty=fullName> по умолчанию выполняют сортировку с учетом языка и региональных параметров, используя свойство `Thread.CurrentCulture`.  Если строки используются в качестве ключей, свойство `Thread.CurrentCulture` может влиять на сортировку и поиск в <xref:System.Collections.SortedList>.  Чтобы получать результаты, не зависящие от языка и региональных параметров, при использовании классов и методов в пространстве имен `Collections` необходимо следовать рекомендациям, приведенным в этом разделе.  
  
 **Примечание**. В результате передачи свойства <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName> методу сравнения сравнение выполняется без учета языка и региональных параметров.  Однако это не приводит к нелингвистическому сравнению, например для путей к файлам, разделов реестра и переменных среды.  Кроме того, при этом не поддерживается принятие решений системы безопасности на основе результатов сравнения.  Для выполнения нелингвистического сравнения и принятия решений системы безопасности на основе результатов сравнения необходимо использовать метод сравнения, принимающий значение <xref:System.StringComparison>.  В этом случае приложение должно передавать значение <xref:System.StringComparison>.  
  
## Использование классов CaseInsensitiveComparer и CaseInsensitiveHashCodeProvider  
 Конструкторы по умолчанию классов `CaseInsensitiveHashCodeProvider` и `CaseInsensitiveComparer` инициализируют новый экземпляр класса с использованием значения `Thread.CurrentCulture`, в результате чего язык и региональные параметры учитываются.  В следующем примере кода показан конструктор для класса `Hashtable`, учитывающий язык и региональные параметры, поскольку в нем используются конструкторы `CaseInsensitiveHashCodeProvider` и `CaseInsensitiveComparer` по умолчанию.  
  
```vb  
internalHashtable = New Hashtable(CaseInsensitiveHashCodeProvider.Default, CaseInsensitiveComparer.Default)  
  
```  
  
```csharp  
internalHashtable = new Hashtable(CaseInsensitiveHashCodeProvider.Default, CaseInsensitiveComparer.Default);  
```  
  
 Если требуется создать не учитывающий язык и региональные параметры объект `Hashtable` с использованием классов `CaseInsensitiveComparer` и `CaseInsensitiveHashCodeProvider`, необходимо инициализировать новые экземпляры этих классов с помощью конструкторов, принимающих параметр `culture`.  В качестве параметра `culture` укажите значение <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>.  В следующем примере кода показан конструктор объекта `Hashtable`, не учитывающего язык и региональные параметры.  
  
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
  
## Использование метода CollectionsUtil.CreateCaseInsensitiveHashTable  
 Метод `CollectionsUtil.CreateCaseInsensitiveHashTable` удобно использовать для создания экземпляра класса `Hashtable`, который не учитывает регистр строк.  Однако все перегруженные версии метода `CollectionsUtil.CreateCaseInsensitiveHashTable` учитывают язык и региональные параметры, поскольку в них используется свойство `Thread.CurrentCulture`.  С помощью этого метода невозможно создать объект `Hashtable`, не учитывающий язык и региональные параметры.  Чтобы создать объект `Hashtable`, не учитывающий язык и региональные параметры, следует использовать конструктор `Hashtable`, который принимает параметр `culture`.  В качестве значения параметра `culture` укажите `CultureInfo.InvariantCulture`.  В следующем примере кода показан конструктор объекта `Hashtable`, не учитывающего язык и региональные параметры.  
  
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
## Использование класса SortedList  
 Класс `SortedList` представляет коллекцию упорядоченных по ключам пар "ключ\-значение", доступ к которым осуществляется по ключу и по индексу.  При использовании объекта `SortedList`, в котором ключами являются строки, на сортировку и поиск может повлиять значение свойства `Thread.CurrentCulture`.  Чтобы поведение объекта `SortedList` не зависело от языка и региональных параметров, необходимо создать объект `SortedList` с использованием одного из конструкторов, принимающих параметр `comparer`.  Параметр `comparer` задает реализацию интерфейса <xref:System.Collections.IComparer>, используемую при сравнении ключей.  В качестве значения этого параметра необходимо указать пользовательский класс сравнения, использующий для сравнения ключей свойство `CultureInfo.InvariantCulture`.  В следующем примере показан не зависящий от языка и региональных параметров пользовательский класс сравнения, который можно задать в качестве параметра `comparer` конструктора `SortedList`.  
  
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
  
 В общем случае при использовании объекта `SortedList` для работы со строками без указания пользовательского инвариантного класса сравнения изменение значения `Thread.CurrentCulture` после заполнения списка может сделать этот список недействительным.  
  
## Использование метода ArrayList.Sort  
 Перегруженные версии метода `ArrayList.Sort` по умолчанию выполняют сортировку с учетом языка и региональных параметров, используя свойство `Thread.CurrentCulture`.  Результаты могут отличаться в разных культурах из\-за отличий в порядке сортировки.  Чтобы результаты не зависели от языка и региональных параметров, следует использовать перегруженные версии этого метода, которые принимают реализацию `IComparer`.  В качестве значения параметра `comparer` необходимо указать пользовательский инвариантный класс сравнения, использующий свойство `CultureInfo.InvariantCulture`.  Пример настраиваемого инвариантного класса сравнения приведен в разделе [Использование класса SortedList](#cpconperformingculture-insensitivestringoperationsincollectionsanchor1).  
  
## См. также  
 <xref:System.Collections.CaseInsensitiveComparer>   
 <xref:System.Collections.CaseInsensitiveHashCodeProvider>   
 <xref:System.Collections.ArrayList.Sort%2A?displayProperty=fullName>   
 <xref:System.Collections.SortedList>   
 <xref:System.Collections.Hashtable>   
 <xref:System.Collections.IComparer>   
 [Выполнение строковых операций, не зависящих от языка и региональных параметров](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)   
 [Метод CollectionsUtil.CreateCaseInsensitiveHashTable](frlrfSystemCollectionsSpecializedCollectionsUtilClassCreateCaseInsensitiveHashtableTopic)