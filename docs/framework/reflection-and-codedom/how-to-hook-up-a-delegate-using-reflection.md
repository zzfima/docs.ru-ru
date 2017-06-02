---
title: "How to: Hook Up a Delegate Using Reflection | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "events [.NET Framework], adding event handlers with reflection"
  - "reflection, adding event-handler delegates"
  - "delegates [.NET Framework], adding event handlers with reflection"
ms.assetid: 076ee62d-a964-449e-a447-c31b33518b81
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# How to: Hook Up a Delegate Using Reflection
При использовании отражения для загрузки и запуска сборок невозможно использовать функциональные возможности языка, такие как оператор C\# `+=` или [оператор AddHandler](../../../ocs/visual-basic/language-reference/statements/addhandler-statement.md) в Visual Basic, для подключения событий.  В следующих процедурах показано, как подключить существующий метод к событию посредством получения всех необходимых типов через отражение и как создать динамический метод с помощью порожденного отражения и подключить этот метод к событию.  
  
> [!NOTE]
>  Другой способ подключения делегата, обрабатывающего событие, см. в примере кода для метода <xref:System.Reflection.EventInfo.AddEventHandler%2A> класса <xref:System.Reflection.EventInfo>.  
  
### Чтобы подключить делегат с помощью отражения  
  
1.  Загрузите сборку, которая содержит тип, создающий события.  Как правило, сборки загружаются с помощью метода <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>.  Чтобы не усложнять этот пример, используется производная форма из текущей сборки, чтобы для загрузки текущей сборки использовался метод <xref:System.Reflection.Assembly.GetExecutingAssembly%2A>.  
  
     [!code-cpp[HookUpDelegate#3](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#3)]
     [!code-csharp[HookUpDelegate#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#3)]
     [!code-vb[HookUpDelegate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#3)]  
  
2.  Получите объект <xref:System.Type>, который представляет тип, и создайте экземпляр типа.  Метод <xref:System.Activator.CreateInstance%28System.Type%29> используется в следующем кода, так как эта форма имеет конструктор по умолчанию.  Существует несколько других перегрузок метода <xref:System.Activator.CreateInstance%2A>, которые можно использовать, если создаваемый тип не имеет конструктора по умолчанию.  Новый экземпляр сохраняется как тип <xref:System.Object> для поддержки утверждения, что об этой сборке ничего не известно. \(Отражение позволяет получить типы в сборке, заведомо не зная их имена.\)  
  
     [!code-cpp[HookUpDelegate#4](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#4)]
     [!code-csharp[HookUpDelegate#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#4)]
     [!code-vb[HookUpDelegate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#4)]  
  
3.  Получите объект <xref:System.Reflection.EventInfo>, который представляет событие, и используйте свойство <xref:System.Reflection.EventInfo.EventHandlerType%2A> для получения типа делегата, используемого для обработки события.  В следующем коде получается объект <xref:System.Reflection.EventInfo> для события <xref:System.Windows.Forms.Control.Click>.  
  
     [!code-cpp[HookUpDelegate#5](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#5)]
     [!code-csharp[HookUpDelegate#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#5)]
     [!code-vb[HookUpDelegate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#5)]  
  
4.  Получите объект <xref:System.Reflection.MethodInfo>, представляющий метод, обрабатывающий событие.  Полный программный код в подразделе Пример этого раздела содержит метод, который соответствует сигнатуре делегата <xref:System.EventHandler>, который обрабатывает событие <xref:System.Windows.Forms.Control.Click>, однако также можно создавать динамические методы во время выполнения.  Подробности см. в соответствующей процедуре создания обработчика события во время выполнения, используя динамический метод.  
  
     [!code-cpp[HookUpDelegate#6](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#6)]
     [!code-csharp[HookUpDelegate#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#6)]
     [!code-vb[HookUpDelegate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#6)]  
  
5.  Создайте экземпляр делегата с помощью метода <xref:System.Delegate.CreateDelegate%2A>.  Этот метод является статическим \(`Shared` в Visual Basic\), поэтому следует предоставить тип делегата.  Рекомендуется использовать перегрузки метода <xref:System.Delegate.CreateDelegate%2A>, принимающие <xref:System.Reflection.MethodInfo>.  
  
     [!code-cpp[HookUpDelegate#7](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#7)]
     [!code-csharp[HookUpDelegate#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#7)]
     [!code-vb[HookUpDelegate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#7)]  
  
6.  Получите метод доступа `add` и вызовите его для подключения события.  Все события имеют метод доступа `add` и метод доступа `remove`, которые скрыты с помощью синтаксиса в высокоуровневых языках.  Например, в C\# используется оператор `+=` для подключения событий, а в Visual Basic используется [оператор AddHandler](../../../ocs/visual-basic/language-reference/statements/addhandler-statement.md).  В следующем коде получается метод доступа `add` для события <xref:System.Windows.Forms.Control.Click> и вызывается с поздней привязкой, передавая в него экземпляр делегата.  Аргументы должны передаваться в качестве массива.  
  
     [!code-cpp[HookUpDelegate#8](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#8)]
     [!code-csharp[HookUpDelegate#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#8)]
     [!code-vb[HookUpDelegate#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#8)]  
  
7.  Проверьте событие.  В следующем фрагменте кода показана форма, определенная в примере кода.  Щелчок формы приводит к вызову обработчика события.  
  
     [!code-cpp[HookUpDelegate#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#12)]
     [!code-csharp[HookUpDelegate#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#12)]
     [!code-vb[HookUpDelegate#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#12)]  
  
<a name="procedureSection1"></a>   
### Чтобы создать обработчик события во время выполнения с помощью динамического метода  
  
1.  Методы обработчика события могут быть созданы во время выполнения с помощью облегченных динамических методов и порождения отражения.  Чтобы создать обработчик события будут необходимы тип возвращаемого значения и типы параметров делегата.  Их можно получить посредством просмотра метода `Invoke`, относящегося к делегату.  В следующем примере кода используются методы `GetDelegateReturnType` и `GetDelegateParameterTypes` для получения этих сведений.  Код этих методов можно найти в подразделе Пример этого раздела.  
  
     Нет необходимости называть <xref:System.Reflection.Emit.DynamicMethod>, поэтому можно использовать пустую строку.  В следующем коде последний аргумент связывает динамический метод с текущим типом, предоставляя доступ делегата ко всем открытым и закрытым элементам класса `Example`.  
  
     [!code-cpp[HookUpDelegate#9](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#9)]
     [!code-csharp[HookUpDelegate#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#9)]
     [!code-vb[HookUpDelegate#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#9)]  
  
2.  Создайте основную часть метода.  Этот метод загружает строку, вызывает перегрузку метода <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=fullName>, которая принимает строку, берет возвращаемое значение со стека \(потому что обработчик не имеет типа возвращаемого значения\) и возвращается.  Дополнительные сведения о выпуске динамических методов см. в разделе [How to: Define and Execute Dynamic Methods](../../../docs/framework/reflection-and-codedom/how-to-define-and-execute-dynamic-methods.md).  
  
     [!code-cpp[HookUpDelegate#10](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#10)]
     [!code-csharp[HookUpDelegate#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#10)]
     [!code-vb[HookUpDelegate#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#10)]  
  
3.  Завершите динамический метод посредством вызова метода <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A>.  Используйте метод доступа `add` для добавления делегата в список вызова для этого события.  
  
     [!code-cpp[HookUpDelegate#11](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#11)]
     [!code-csharp[HookUpDelegate#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#11)]
     [!code-vb[HookUpDelegate#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#11)]  
  
4.  Проверьте событие.  В следующем фрагменте кода загружается форма, определенная в примере кода.  Щелчок этой формы приводит к вызову предварительно определенного обработчика события и выпущенного обработчика события.  
  
     [!code-cpp[HookUpDelegate#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#12)]
     [!code-csharp[HookUpDelegate#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#12)]
     [!code-vb[HookUpDelegate#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#12)]  
  
## Пример  
 В следующем примере кода показано, как подключить существующий метод к событию с помощью отражения, а также как использовать класс <xref:System.Reflection.Emit.DynamicMethod> для выпуска метода во время выполнения и подключить его к событию.  
  
 [!code-cpp[HookUpDelegate#1](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#1)]
 [!code-csharp[HookUpDelegate#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#1)]
 [!code-vb[HookUpDelegate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#1)]  
  
## Компиляция кода  
  
-   Код содержит операторы C\# `using` \(`Imports` в Visual Basic\), необходимые для компиляции.  
  
-   Отсутствует необходимость в дополнительных ссылках на сборки в целях компиляции из командной строки.  В Visual Studio необходимо добавить ссылку в System.Windows.Forms.dll, так как этот пример является приложением консоли.  
  
-   Откомпилируйте код из командной строки, используя команды csc.exe, vbc.exe или cl.exe.  Чтобы откомпилировать код в Visual Studio, поместите его в шаблон проекта консольного приложения.  
  
## См. также  
 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>   
 <xref:System.Reflection.Emit.DynamicMethod>   
 <xref:System.Activator.CreateInstance%2A>   
 <xref:System.Delegate.CreateDelegate%2A>   
 [How to: Define and Execute Dynamic Methods](../../../docs/framework/reflection-and-codedom/how-to-define-and-execute-dynamic-methods.md)   
 [Reflection](../../../docs/framework/reflection-and-codedom/reflection.md)