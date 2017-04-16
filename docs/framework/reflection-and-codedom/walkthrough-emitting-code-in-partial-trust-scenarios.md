---
title: "Walkthrough: Emitting Code in Partial Trust Scenarios | Microsoft Docs"
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
  - "reflection emit, anonymously hosted dynamic methods"
  - "partial trust, reflection"
  - "partial trust, emitting dynamic methods"
  - "reflection emit, partial trust scenarios"
  - "anonymously hosted dynamic methods [.NET Framework]"
  - "emitting dynamic assemblies,partial trust scenarios"
  - "reflection emit, dynamic methods"
  - "dynamic methods"
ms.assetid: c45be261-2a9d-4c4e-9bd6-27f0931b7d25
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Walkthrough: Emitting Code in Partial Trust Scenarios
При порождение отражения используется тот же набор интерфейса API полного или частичного доверия, однако для некоторых функциональных возможностей требуются особые разрешения в коде с частичным доверием.  Кроме того, в порождении отражения имеется функциональная возможность — анонимно размещенные динамические методы, которые предназначены для использования или при частичном доверии, или в прозрачных для безопасности сборках.  
  
> [!NOTE]
>  В версиях, предшествовавших [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)], для выпуска кода требовалось разрешение <xref:System.Security.Permissions.ReflectionPermission> с флагом <xref:System.Security.Permissions.ReflectionPermissionFlag?displayProperty=fullName>.  Это разрешение по умолчанию включено в именованные наборы разрешений `FullTrust` и `Intranet`, но отсутствует в наборе разрешений сети `Internet`.  Поэтому библиотека может использоваться при частичном доверии только в том случае, если она имела атрибут <xref:System.Security.SecurityCriticalAttribute> и также выполнила метод <xref:System.Security.PermissionSet.Assert%2A> для <xref:System.Security.Permissions.ReflectionPermissionFlag>.  Подобные библиотеки нуждаются в тщательном обеспечении безопасности, так как ошибки в коде могут привести к серьезным брешам в системе безопасности.  В платформе [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] код может быть выпущен в сценариях частичного доверия без формирования любых требований к безопасности, так как создание кода по существу не является привилегированной операцией.  То есть созданный код обладает не большими разрешениями, чем выпустившая его сборка.  Это позволяет библиотекам выпускать код, прозрачный для безопасности, и устраняет необходимость в подтверждении <xref:System.Security.Permissions.ReflectionPermissionFlag>, что упрощает задачу написания безопасной библиотеки, так как тщательная проработка безопасности будет не нужна.  
  
 В данном пошаговом руководстве рассмотрены следующие задачи:  
  
-   [Настройка простой "песочницы" для проверки кода с частичным доверием](#Setting_up).  
  
    > [!IMPORTANT]
    >  Это простой способ поэкспериментировать с кодом в режиме частичного доверия.  Чтобы выполнить код, полученный из ненадежных мест, см. раздел [How to: Run Partially Trusted Code in a Sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md).  
  
-   [Выполнение кода в доменах приложений с частичным доверием](#Running_code).  
  
-   [Использование анонимно размещенных динамических методов для выпуска и выполнения кода при частичном доверии](#Using_methods).  
  
 Дополнительные сведения о выпуске кода в сценариях с частичным доверием см. в разделе [Security Issues in Reflection Emit](../../../docs/framework/reflection-and-codedom/security-issues-in-reflection-emit.md).  
  
 Полный код, показанный в данных процедурах, см. в разделе [Пример](#Example) в конце этого руководства.  
  
<a name="Setting_up"></a>   
## Настройка расположений с частичным доверием  
 В следующих двух процедурах показано, как настроить расположения, из которых можно проверить код с частичным доверием.  
  
-   В первой процедуре показано, как создать изолированный домен приложения, в котором коду предоставляются разрешения Интернета.  
  
-   Во второй процедуре демонстрируется, как добавить разрешение <xref:System.Security.Permissions.ReflectionPermission> с флагом <xref:System.Security.Permissions.ReflectionPermissionFlag?displayProperty=fullName> в домен приложения с частичным доверием, чтобы разрешить доступ к конфиденциальным данным в сборках с равным или меньшим доверием.  
  
### Создание изолированных доменов приложений  
 Чтобы создать домен приложения, в котором сборки будут работать при частичном доверии, необходимо указать набор разрешений, которые должны быть предоставлены сборкам, посредством использования перегрузки метода [AppDomain.CreateDomain\(String, Evidence, AppDomainSetup, PermissionSet, StrongName\<xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=fullName> для создания домена приложения.  Самым простым способом указания набора разрешений является получение именованного набора разрешений из политики безопасности.  
  
 В следующей процедуре создается изолированный домен приложения, в котором код будет выполняться при частичном доверии для проверки сценариев, в которых с помощью выпущенного кода можно получить доступ только к открытым элементам открытого типа.  В последующих процедурах показано, как добавить <xref:System.Security.Permissions.ReflectionPermissionFlag> для проверки сценариев, в которых с помощью выпущенного кода можно получить доступ к закрытым типам и элементам в сборках, которым предоставлены равнозначные или меньшие разрешения.  
  
##### Чтобы создать домен приложения с частичным уровнем доверия  
  
1.  Создайте набор разрешений, предоставляемых сборкам в изолированном домене приложений.  В данном случае используется набор разрешений зоны Интернета.  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#2)]
     [!code-vb[HowToEmitCodeInPartialTrust#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#2)]  
  
2.  Создайте объект <xref:System.AppDomainSetup> для инициализации домена приложения с путем приложения.  
  
    > [!IMPORTANT]
    >  Для простоты в этом примере кода используется текущая папка.  Чтобы выполнить код, фактически полученный из Интернета, используйте отдельную папку для ненадежного кода, как описано в разделе [How to: Run Partially Trusted Code in a Sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md).  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#3)]
     [!code-vb[HowToEmitCodeInPartialTrust#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#3)]  
  
3.  Создайте домен приложения, задавая данные для настройки домена приложения и набор прав для всех сборок, выполняемых в домене приложения.  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#5)]
     [!code-vb[HowToEmitCodeInPartialTrust#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#5)]  
  
     С помощью последнего параметра перегрузки метода [AppDomain.CreateDomain\(String, Evidence, AppDomainSetup, PermissionSet, StrongName\<xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=fullName> можно указать набор сборок, которым будет предоставлено полное доверия, а не набор правил домена приложения.  Нет необходимости указывать сборки [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], используемые приложением, так как эти сборки находятся в глобальном кэше сборок.  Сборки, находящиеся в глобальном кэше сборок, всегда имеют полное доверие.  Этот параметр можно использовать для указания сборок со строгими именами, которые не находятся в глобальном кэше сборок.  
  
### Добавление доступа RestrictedMemberAccess к изолированным доменам  
 Ведущие приложения могут разрешать доступ анонимно размещенных динамических методов к конфиденциальным данным в сборках, уровень доверия которых не превышает уровень доверия сборки, выпускающей код.  Чтобы разрешить эту ограниченную возможность пропуска проверок видимости, выполняемых JIT\-компилятором, ведущее приложение добавляет объект <xref:System.Security.Permissions.ReflectionPermission> с флагом <xref:System.Security.Permissions.ReflectionPermissionFlag?displayProperty=fullName> \(RMA\) в набор правил.  
  
 Например, основное приложение может предоставить интернет\-приложениям интернет\-разрешения и RMA, так что интернет\-приложение может выпустить код, который будет получить доступ к конфиденциальным данным в собственных сборках.  Так как доступ ограничен сборками с таким же или меньшим уровнем доверия, интернет\-приложение не может получить доступ к элементам сборок с полным довериям, таким как сборки [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].  
  
> [!NOTE]
>  Чтобы предотвратить повышение уровня привилегии, при создании анонимно размещенных динамических методов включаются также сведения стека для выпускающей сборки.  При вызове этого метода проверяются сведения стека.  Поэтому вызванный из кода с полным уровнем доверия анонимно размещенный динамический метод все так же ограничен уровнем доверия выпускающей сборки.  
  
##### Чтобы создать домен приложения с частичным доверием и RMA  
  
1.  Создайте новый объект <xref:System.Security.Permissions.ReflectionPermission> с флагом <xref:System.Security.Permissions.ReflectionPermissionFlag> \(RMA\) и используйте метод <xref:System.Security.PermissionSet.SetPermission%2A?displayProperty=fullName> для добавления разрешения в набор прав.  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#7)]
     [!code-vb[HowToEmitCodeInPartialTrust#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#7)]  
  
     Метод <xref:System.Security.PermissionSet.AddPermission%2A> добавляет это разрешение в набор правил, если его там еще нет.  Если разрешение уже включено в набор правил, указанные флаги добавляются в существующее разрешение.  
  
    > [!NOTE]
    >  RMA — это функциональная возможность анонимно размещенных динамических методов.  Если обычные динамические методы пропускают проверку видимости, выполняемую JIT\-компилятором, выдаваемому коду требуется полное доверие.  
  
2.  Создайте домен приложения, указав данные настройки домена приложения и набор прав.  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#8)]
     [!code-vb[HowToEmitCodeInPartialTrust#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#8)]  
  
<a name="Running_code"></a>   
## Выполнение кода в изолированных доменах приложения  
 В следующей процедуре объясняется, как следует определить класс с помощью методов, которые могут быть выполнены в домене приложения, как создать экземпляр класса в домене и как выполнить его методы.  
  
#### Чтобы определить и выполнить метод в домене приложения  
  
1.  Определите класс, производный от класса <xref:System.MarshalByRefObject>.  Это позволит создать экземпляры класса в других доменах приложения, а также вызывать методы за пределами домена приложения.  Класс в этом примере назван `Worker`.  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#10)]
     [!code-vb[HowToEmitCodeInPartialTrust#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#10)]  
  
2.  Определите открытый метод, содержащий код, который следует выполнить.  В этом примере в коде выпускается простой динамический метод, создается делегат для выполнения этого метода и вызывается делегат.  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#11)]
     [!code-vb[HowToEmitCodeInPartialTrust#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#11)]  
  
3.  В основной программе обратите внимание на отображаемое имя сборки.  Это имя используется при создании экземпляров класса `Worker` в изолированном домене приложения.  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#14](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#14)]
     [!code-vb[HowToEmitCodeInPartialTrust#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#14)]  
  
4.  В основной программе создайте изолированный домен приложения, как описано в [первой процедуре](#Setting_up) этого пошагового руководства.  Нет необходимости добавлять любые разрешения в набор разрешений `Internet`, так как метод `SimpleEmitDemo` использует только открытые методы.  
  
5.  В основной программе создайте экземпляр класса `Worker` в изолированном домене приложения.  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#12)]
     [!code-vb[HowToEmitCodeInPartialTrust#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#12)]  
  
     Метод <xref:System.AppDomain.CreateInstanceAndUnwrap%2A> создает объект в целевом домене приложения и возвращает прокси, который может использоваться для вызова свойств и методов объекта.  
  
    > [!NOTE]
    >  При использовании этого кода в [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], необходимо изменить имя класса для включения пространства имен.  По умолчанию пространство имен носит имя проекта.  Например, если проект называется "PartialTrust", именем класса должно являться "PartialTrust.Worker".  
  
6.  Добавьте код для вызова метода `SimpleEmitDemo`.  Вызов маршалируется за пределы домена приложения, а код выполняется в изолированном домене приложения.  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#13)]
     [!code-vb[HowToEmitCodeInPartialTrust#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#13)]  
  
<a name="Using_methods"></a>   
## Использование анонимно размещенных динамических методов  
 Анонимно размещенные динамические методы связаны со прозрачной сборкой, предоставленной системой.  Следовательно, содержащийся в них код является прозрачным.  С другой стороны, обычные динамические методы должны быть связаны с существующим модулем \(явно или неявно из связанного типа\) и получают свой уровень безопасности от этого модуля.  
  
> [!NOTE]
>  Единственным способом сопоставления динамического метода со сборкой, предоставляющей анонимное размещение, — это использование конструкторов, описанных в следующей процедуре.  Можно явно указать модуль в анонимно размещающей сборке.  
  
 Обычные динамические методы имеют доступ к внутренним элементам модуля, с которым они связаны, или к закрытым элементам типа, с которым они связаны.  Так как анонимно размещенные динамические методы отделены от другого кода, они не имеют доступа к закрытым данным.  Однако у них имеется ограниченная возможность пропускать проверку видимости, выполняемых JIT\-компилятором, для получения доступа к конфиденциальным данным.  Эта возможность огранивается сборками, уровень доверия которых не превышает уровень доверия сборки, выпустившей этот код.  
  
 Чтобы предотвратить повышение уровня привилегии, при создании анонимно размещенных динамических методов включаются также сведения стека для выпускающей сборки.  При вызове этого метода проверяются сведения стека.  Анонимно размещенный динамический метод, вызванный из кода с полным доверием, также ограничен уровнем доверия выпустившей его сборки.  
  
#### Чтобы использовать анонимно размещенные динамические методы  
  
-   Создайте анонимно размещенный динамический метод путем использования конструктора, который не указывает связанный модуль или тип.  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#15](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#15)]
     [!code-vb[HowToEmitCodeInPartialTrust#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#15)]  
  
     Если анонимно размещенный динамический метод использует только открытые типы и методы, ему не требуется ограниченный доступ к элементам и он может не пропускать проверки видимости, выполняемые JIT\-компилятором.  
  
     Специальных разрешений для выпуска динамического метода не требуется, однако выпущенный код нуждается в разрешениях, которые требуются для используемых в этом коде типов и методов.  Например, если выпущенный код вызывает метод, который получает доступ к файлу, необходимо разрешение <xref:System.Security.Permissions.FileIOPermission>.  Если уровень доверия не включает это разрешение, при выполнении выпущенного кода создается исключение безопасности.  Приведенный здесь код выпускает динамический метод, который использует только метод <xref:System.Console.WriteLine%2A?displayProperty=fullName>.  Поэтому код может быть выполнен в расположениях с частичным доверием.  
  
-   Кроме того, создайте анонимно размещенный динамический метод с ограниченной возможности пропуска проверок видимости, выполняемых JIT\-компилятором, посредством использования конструктора [DynamicMethod\(String, Type, Type\<xref:System.Reflection.Emit.DynamicMethod.%23ctor%28System.String%2CSystem.Type%2CSystem.Type%5B%5D%2CSystem.Boolean%29> и указания значения `true` для параметра `restrictedSkipVisibility`.  
  
     [!code-csharp[HowToEmitCodeInPartialTrust#16](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#16)]
     [!code-vb[HowToEmitCodeInPartialTrust#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#16)]  
  
     Ограничение заключается в том, что анонимно размещенный динамический метод может получать доступ к конфиденциальным данным только в сборках, уровень доверия которых не превышает уровень доверия выпускающей сборки.  Например, если динамический метод выполняется с доверием Интернета, он может получить доступ к конфиденциальным данным в других сборках, также выполняемых с доверием Интернета, но ему не будут доступны конфиденциальные данные сборок [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].  Сборки [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] установлены в глобальном кэше сборок и всегда обладают полным доверием.  
  
     Анонимно размещенные динамические методы могут использовать эту ограниченную возможность пропуска проверок видимости, выполняемых JIT\-компилятором, только в том случае, если приложение предоставляет разрешение <xref:System.Security.Permissions.ReflectionPermission> с флагом <xref:System.Security.Permissions.ReflectionPermissionFlag?displayProperty=fullName>.  Это разрешение требуется при вызове метода.  
  
    > [!NOTE]
    >  Сведения стека вызовов для выпускающей сборки включаются при создании динамического метода.  Поэтому запрос делается для разрешений выпускающей сборки, а не для сборки, вызывающей метод.  Это препятствует выполнению выпущенного кода с повышенным уровнем разрешений.  
  
     [Полный пример кода](#Example) в конце этого пошагового руководства служит для демонстрации использования ограниченного доступа к элементам.  Класс `Worker` содержит метод, который может создавать анонимно размещенные динамические методы с возможностью пропускать проверки видимости или без нее, а в этом примере показан результат выполнения этого метода в доменах приложения с другими уровнями доверия.  
  
    > [!NOTE]
    >  Ограниченная возможность пропуска проверок видимости — это функциональная возможность анонимно размещенных динамических методов.  Если обычные динамические методы пропускают проверку видимости, выполняемую JIT\-компилятором, им необходимо предоставить полное доверие.  
  
<a name="Example"></a>   
## Пример  
  
### Описание  
 В следующем примере кода демонстрируется использование флага <xref:System.Security.Permissions.ReflectionPermissionFlag> для разрешения невыполнения проверки видимости JIT\-компилятором анонимно размещенными динамическими методами, но только в тех случаях, когда целевой уровень доверия целевого элемента не превышает уровень доверия сборки, выпустившей код.  
  
 В примере определяется класс `Worker`, который может быть упакован и передан через границы домена приложений.  Этот класс содержит две перегрузки метода `AccessPrivateMethod`, которые выпускают и выполняют динамические методы.  Первая перегрузка выпускает динамический метод, который вызывает закрытый метод `PrivateMethod` класса `Worker`. Она может вызвать динамический метод с проверкой видимости с помощью JIT\-компилятора или без нее.  Вторая перегрузка выпускает динамический метод, который получает доступ к свойству `internal` \(свойство `Friend` в Visual Basic\) класса <xref:System.String>.  
  
 В этом примере используется вспомогательный метод для создания набора прав, ограниченного разрешениями `Internet`, а затем создается домен приложения с помощью перегрузки метода [AppDomain.CreateDomain\(String, Evidence, AppDomainSetup, PermissionSet, StrongName\<xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=fullName> для указания необходимости использовать этот набор прав для всего выполняемого кода в домене.  В примере создается экземпляр класса `Worker` в домене приложения, затем дважды выполняется метод `AccessPrivateMethod`.  
  
-   При первом запуске метода `AccessPrivateMethod` принудительно выполняются проверки видимости с помощью JIT\-компилятора.  Динамический метод завершается со сбоем после вызова, так как проверки видимости с помощью JIT\-компилятора не дают ему получить доступ к закрытому методу.  
  
-   При втором запуске метода `AccessPrivateMethod` проверки видимости с помощью JIT\-компилятора не выполняются.  Компиляция динамического метода завершается со сбоем, так как набор разрешений `Internet` не предоставляет достаточных разрешений для пропуска проверок видимости.  
  
 В этом примере в набор прав добавляется разрешение <xref:System.Security.Permissions.ReflectionPermission> с флагом <xref:System.Security.Permissions.ReflectionPermissionFlag?displayProperty=fullName>.  Затем в примере создается второй домен и указывается, что весь код, выполняемый в домене, получает разрешения из нового набора разрешений.  В примере создается экземпляр класса `Worker` в домене приложения, затем дважды выполняются перегрузки метода `AccessPrivateMethod`.  
  
-   Выполняется первая перегрузка метода `AccessPrivateMethod`, и проверки видимости с помощью JIT\-компилятора пропускаются.  Динамический метод успешно компилируется и выполняется, так как сборка, выпустившая код является такой же, что и сборка, содержащая закрытый метод.  Поэтому уровни доверия одинаковы.  Если приложение, содержащее класс `Worker` содержит несколько сборок, этот же процесс пройдет успешно для любой из сборок, так как они все будут иметь один и тот же уровень доверия.  
  
-   Выполняется вторая перегрузка метода `AccessPrivateMethod`, и проверки видимости с помощью JIT\-компилятора снова пропускаются.  На этом раз компиляция динамического метода завершается со сбоем, потому что происходит попытка получить доступ к свойству `internal``FirstChar` класса <xref:System.String>.  Сборка, содержащая класс <xref:System.String>, имеет полное доверие.  Следовательно, уровень доверия выше, чем уровень доверия сборки, выпустившей код.  
  
 В этом сравнении показано, как <xref:System.Security.Permissions.ReflectionPermissionFlag?displayProperty=fullName> позволяет пропускать проверки видимости в коде с неполным доверием, предназначенные для другого кода с неполным доверием, без нарушения безопасности доверенного кода.  
  
### Код  
 [!code-csharp[HowToEmitCodeInPartialTrust#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/cs/source.cs#1)]
 [!code-vb[HowToEmitCodeInPartialTrust#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEmitCodeInPartialTrust/vb/source.vb#1)]  
  
## Компиляция кода  
  
-   При создании этого примера кода в [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] необходимо изменить имя класса, добавляя пространство имен при передаче класса в метод <xref:System.AppDomain.CreateInstanceAndUnwrap%2A>.  По умолчанию пространство имен носит имя проекта.  Например, если проект называется "PartialTrust", именем класса должно являться "PartialTrust.Worker".  
  
## См. также  
 [Security Issues in Reflection Emit](../../../docs/framework/reflection-and-codedom/security-issues-in-reflection-emit.md)   
 [How to: Run Partially Trusted Code in a Sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)