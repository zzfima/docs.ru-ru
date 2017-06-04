---
title: "Enhancing Debugging with the Debugger Display Attributes | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "debugger, display attributes"
  - "DebuggerTypeProxyAttribute attribute"
  - "debugging [.NET Framework], debugger display attributes"
  - "DebuggerDisplayAttribute attribute"
  - "display attributes for debugger"
  - "DebuggerBrowsableAttribute attribute"
ms.assetid: 72bb7aa9-459b-42c4-9163-9312fab4c410
caps.latest.revision: 7
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# Enhancing Debugging with the Debugger Display Attributes
Атрибуты просмотра отладчика позволяют разработчику типа, который задает и хорошо понимает поведение среды выполнения данного типа, также определять, как будет выглядеть тип при отображении в отладчике.   Помимо этого, атрибуты просмотра отладчика, которые предоставляют свойство `Target`, могут применяться на уровне сборки пользователями, незнакомыми с исходным кодом.   Атрибут <xref:System.Diagnostics.DebuggerDisplayAttribute> управляет тем, как тип или член отображаются в окнах переменных отладчика.  Атрибут <xref:System.Diagnostics.DebuggerBrowsableAttribute> определяет, будет ли поле или свойство отображаться в окнах переменных отладчика, и каким образом.  Атрибут <xref:System.Diagnostics.DebuggerTypeProxyAttribute> указывает заменяющий тип или прокси для типа и изменяет способ его отображения в окнах отладчика.  При просмотре переменной, у которой есть прокси или заменяющий тип, прокси заменяет исходный тип в окне отладчика**.** Окно переменных отладчика отображает толькооткрытые члены прокси\-типа.  Закрытые члены не отображаются.  
  
## Использование атрибута DebuggerDisplay  
 У конструктора <xref:System.Diagnostics.DebuggerDisplayAttribute.%23ctor%2A> есть один аргумент: строка, отображаемая в столбце значений для экземпляров типа.  Эта строка может содержать фигурные скобки \({ и }\).  Текст внутри пары фигурных скобок интерпретируется как выражение.  Например, выполнение следующего кода на языке C\# приводит к отображению строки "Count \= 4" при выборе знака плюс \(\+\) с целью развертывания отображения отладчика для экземпляра `MyHashtable`:  
  
```  
[DebuggerDisplay("Count = {count}")]  
class MyHashtable  
{  
    public int count = 4;  
}  
```  
  
 Атрибуты, применяемые для свойств, на которые ссылается выражение, не обрабатываются.  Для компилятора С\# разрешены общие выражения, которые обращаются к этой ссылке на текущий экземпляр целевого типа только неявным образом.  Такое выражение ограничено, у него нет доступа к псевдонимам, локальным переменным или указателям.  В коде С\# можно использовать общие выражения, заключенные в фигурные скобки, которые обращаются к указателю `this` на текущий экземпляр целевого типа только неявным образом.  
  
 Например, если в C\# объект был переопределен `ToString()`, то отладчик вызовет переопределение и отобразит его результат вместо стандартного `{<typeName>}.`. Таким образом, если переопределить `ToString()`, нет необходимости использовать <xref:System.Diagnostics.DebuggerDisplayAttribute>.   Если используется и то и другое, то атрибут <xref:System.Diagnostics.DebuggerDisplayAttribute> будет иметь более высокий приоритет по отношению к переопределению `ToString()`.  
  
## Использование атрибута DebuggerBrowsable  
 Атрибут <xref:System.Diagnostics.DebuggerBrowsableAttribute> применяется к полю или свойству, чтобы определить, каким образом поле или свойство должно отображаться в отладчике.   Конструктор для этого атрибута принимает одно из значений перечисления <xref:System.Diagnostics.DebuggerBrowsableState>, которое задает одно из приведенных ниже состояний:  
  
-   <xref:System.Diagnostics.DebuggerBrowsableState>. Свидетельствует о том, что член в окне данных не отображается.  Например, использование этого значения для атрибута <xref:System.Diagnostics.DebuggerBrowsableAttribute> в каком\-либо поле приводит к удалению этого поля из иерархии; при развертывании включающего типа щелчком по знаку плюс \(\+\) рядом с экземпляром типа это поле не отображается.  
  
-   <xref:System.Diagnostics.DebuggerBrowsableState>. Свидетельствует о том, что член отображается, но по умолчанию не развернут.  Это поведение установлено по умолчанию.  
  
-   <xref:System.Diagnostics.DebuggerBrowsableState> указывает на то, что член сам по себе не отображается, однако отображаются составляющие его объекты, если он находится в массиве или коллекции.  
  
> [!NOTE]
>  Visual Basic в .NET Framework версии 2.0 не поддерживает <xref:System.Diagnostics.DebuggerBrowsableAttribute>.  
  
 Следующий пример кода демонстрирует использование <xref:System.Diagnostics.DebuggerBrowsableAttribute>, чтобы предотвратить отображение свойства, следующего за ним, в окне отладчика для класса:  
  
```  
[DebuggerBrowsable(DebuggerBrowsableState.Never)]  
public static string y = "Test String";  
```  
  
## Использование атрибута DebuggerTypeProxy  
 Атрибут <xref:System.Diagnostics.DebuggerTypeProxyAttribute> следует использовать в тех случаях, когда необходимо внести существенные и принципиальные изменения в отладочное представление типа, сохранив сам тип неизменным.  С помощью атрибута <xref:System.Diagnostics.DebuggerTypeProxyAttribute> можно задать прокси отображения для типа, который позволит разработчикам настраивать представление типа.  Этот атрибут, как и <xref:System.Diagnostics.DebuggerDisplayAttribute>, можно использовать на уровне сборки; в этом случае свойство <xref:System.Diagnostics.DebuggerTypeProxyAttribute.Target%2A> устанавливает тип, для которого будет использоваться прокси.   Рекомендуется использовать данный атрибут для указания закрытого вложенного типа, который образуется внутри типа, к которому применен данный атрибут.  При отображении типа вычислитель выражений, поддерживающий средства просмотра типов, выполняет проверку на наличие этого атрибута.  Если атрибут найден, вычислитель выражений подставляет прокси\-тип отображения в тип, к которому был применен данный атрибут.  
  
 При наличии атрибута <xref:System.Diagnostics.DebuggerTypeProxyAttribute> в окне переменной отладчика отображаются только открытые элементы прокси\-типа.  Закрытые члены не отображаются.  Поведение окна данных не меняется при использовании представлений с расширенными атрибутами.  
  
 Чтобы уменьшить потери производительности, атрибуты для прокси отображения не обрабатываются до тех пор, пока объект не будет развернут. Пользователь может его развернуть, щелкнув знак плюс \(\+\) рядом с типом в окне данных, или с помощью приложения, заданного атрибутом <xref:System.Diagnostics.DebuggerBrowsableAttribute>.  Поэтому рекомендуется не применять атрибуты к типам отображения.  Атрибуты можно и нужно применять в основной части типа отображения.  
  
 В следующем примере кода показано, как с помощью атрибута <xref:System.Diagnostics.DebuggerTypeProxyAttribute> задать тип, который будет использоваться для отладчика в качестве прокси отображения:  
  
```  
  
[DebuggerTypeProxy(typeof(HashtableDebugView))]  
class MyHashtable : Hashtable  
{  
    private const string TestString =   
        "This should not appear in the debug window.";  
  
    internal class HashtableDebugView  
    {  
        private Hashtable hashtable;  
        public const string TestStringProxy =   
            "This should appear in the debug window.";  
  
        // The constructor for the type proxy class must have a   
        // constructor that takes the target type as a parameter.  
        public HashtableDebugView(Hashtable hashtable)  
        {  
            this.hashtable = hashtable;  
        }  
    }  
}  
```  
  
## Пример  
  
### Описание  
 Следующий пример кода можно просмотреть в [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] для ознакомления с результатами применения атрибутов <xref:System.Diagnostics.DebuggerDisplayAttribute>, <xref:System.Diagnostics.DebuggerBrowsableAttribute> и <xref:System.Diagnostics.DebuggerTypeProxyAttribute>.  
  
### Код  
 [!code-cpp[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/cpp/program.cpp#1)]
 [!code-csharp[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/CS/program.cs#1)]
 [!code-vb[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/VB/module1.vb#1)]  
  
## См. также  
 <xref:System.Diagnostics.DebuggerDisplayAttribute>   
 <xref:System.Diagnostics.DebuggerBrowsableAttribute>   
 <xref:System.Diagnostics.DebuggerTypeProxyAttribute>