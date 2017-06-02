---
title: "Действие Property Promotion | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 802196b7-1159-4c05-b41b-d3bfdfcc88d9
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Действие Property Promotion
Этот образец представляет собой законченное решение, в котором средства повышения уровня <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> встраиваются непосредственно в среду разработки рабочих процессов.Предоставляется коллекция элементов конфигурации, действий рабочего процесса и расширений рабочих процессов, которая позволяет упростить использование средства повышения уровня.Кроме того, этот образец включает простой рабочий процесс, в котором демонстрируется использование этой коллекции.  
  
> [!NOTE]
>  Образцы предназначены только для обучения.Они не предназначены для производственной среды и не были проверены в рабочей среде.Корпорация Майкрософт не предоставляет техническую поддержку для этих образцов.  
  
## Предварительные требования  
  
-   Инициализированная база данных <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>  
  
-   [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]  
  
## Образцы проектов  
  
-   Проект **PropertyPromotionActivity** содержит файлы, относящиеся к характерным для повышения уровня элементам конфигурации, действиям рабочего процессам и расширениям рабочего процесса.  
  
-   Проект **CounterServiceApplication** содержит образец рабочего процесса, в котором используется проект **SqlWorkflowInstanceStorePromotion**.  
  
-   Скрипт SQL \(PropertyPromotionActivitySQLSample.sql\), который должен быть запущен применительно к базе данных <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>.  
  
-   Файл решения, который связывает два проекта [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] \(`PropertyPromotionActivity.sln`\)  
  
## Установка и запуск образца  
  
1.  Инициализируйте базу данных сохраняемости рабочих процессов.  
  
    1.  Перейдите в каталог образца \(\\WF\\Basic\\Persistence\\PropertyPromotionActivity\) и запустите пакет CreateInstanceStore.cmd.  
  
    2.  Если права администратора недоступны, создайте имя входа SQL Server.В среде SQL Server Management Studio перейдите к элементу **Безопасность**, **Имена входа**.Щелкните правой кнопкой мыши узел **Имена входа** и создайте новое имя входа.Добавьте своего пользователя ACL к роли SQL, перейдя к элементу **Базы данных**, **InstanceStore**, **Безопасность**.Щелкните правой кнопкой мыши раздел **Пользователи** и выберите команду **Создать пользователя**.Задайте **Имя входа** для пользователя, созданного перед этим.Добавьте пользователя к членам роли базы данных System.Activities.DurableInstancing.InstanceStoreUsers \(и к другим ролям\).Обратите внимание, что пользователь может уже существовать \(например, пользователь dbo\).  
  
2.  Откройте файл решения PropertyPromotionActivity.sln в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
3.  Если хранилище экземпляров создано в базе данных, отличной от локальной установки SQL Server Express, то необходимо обновить строку подключения базы данных.Измените файл App.config, относящийся к **CounterServiceApplication**, задавая значение атрибута `connectionString` на узле `sqlWorkflowInstanceStorePromotion`, чтобы он указывал на базу данных сохраняемости, которая была инициализирована в шаге 1.  
  
4.  Постройте и запустите это решение.Это приведет к запуску службы счетчика WF и вызовет автоматический запуск экземпляра рабочего процесса.  
  
5.  Быстро выделите все строки в представлении \[dbo\].\[CounterService\] в применяемой базе данных сохраняемости \(это представление было добавлено в результате выполнения пакета CreateInstanceStore.cmd в шаге 1\).Появится результирующий набор, аналогичный следующему:  
  
    |InstanceId|CounterValue|CounterValueLastUpdated|  
    |----------------|------------------|-----------------------------|  
    |2FA2C302\-929E\-4C0D\-8C25\-768A3DA20CE5|12|2010\-02\-18 22:48:01.740|  
  
     Продолжая обновлять это представление, обратите внимание, что значения CounterValue и CounterValueLastUpdated изменяются через каждые две секунды.Это интервал, в течение которого счетчик обновляет сам себя.Значения CounterValue и CounterValueLastUpdated представляют свойства с повышенным уровнем для этого рабочего процесса.  
  
## Удаление образца  
  
-   Выполните пакет RemoveInstanceStore.cmd в каталоге образца \(\\WF\\Basic\\Persistence\\PropertyPromotionActivity\).  
  
## Основные сведения об этом образце  
 Образец содержит два проекта и файл SQL:  
  
-   **CounterServiceApplication** — это консольное приложение, в котором размещается простая служба счетчика WF.После получения одностороннего сообщения через конечную точку `Start` рабочий процесс производит отсчет от 0 до 29, увеличивая переменную счетчика через каждые две секунды.После каждого приращения счетчика рабочий процесс сохраняется и свойства с повышенным уровнем обновляются в представлении \[dbo\].\[CounterService\].После запуска консольного приложения это приложение размещает службу WF и отправляет сообщение в конечную точку `Start`, создавая экземпляр счетчика WF.  
  
-   **PropertyPromotionActivity** — это библиотека классов, которая содержит элементы конфигурации, действия рабочего процесса и расширения рабочего процесса, которые используются в **CounterServiceApplication**.  
  
-   Скрипт **PropertyPromotionActivitySQLSample.sql** создает и добавляет представление \[dbo\].\[CounterService\] в базу данных.  
  
### CounterServiceApplication  
  
#### Использование элемента конфигурации SqlWorkflowInstanceStorePromotion  
 Элемент конфигурации `SqlWorkflowInstanceStorePromotion` наследует от элемента конфигурации `SqlWorkflowInstanceStore`, но добавляет дополнительный элемент конфигурации с именем `promotionSets`.Элемент `promotionSets` позволяет пользователю задавать свойства с повышенным уровнем путем настройки.Это файл конфигурации, который используется образцом:  
  
```xml  
<sqlWorkflowInstanceStorePromotion connectionString ="Data Source=.;Initial Catalog=SqlWorkflowInstanceStoreTest;Integrated Security=True;">  
  <promotionSets>  
    <promotionSet name="CounterService">  
      <promotedValue propertyName="Count"/>  
      <promotedValue propertyName="LastIncrementedAt"/>  
    </promotionSet>  
  </promotionSets>  
</sqlWorkflowInstanceStorePromotion>  
```  
  
 Изучите определение для представления \[dbo\].\[CounterService\].  
  
```sql  
create view [dbo].[CounterService] as  
      select [InstanceId],  
 [Value1] as [CounterValue],  
 [Value2] as [CounterValueLastUpdated]  
      from [System.Activities.DurableInstancing].[InstancePromotedProperties]  
      where [PromotionName] = 'CounterService'  
go  
  
```  
  
 При сохранении экземпляра рабочего процесса происходит вставка в представление `InstancePromotedProperties` одной строки для каждого `PromotionSet`, определенного в конфигурации.Эта строка содержит все свойства `PromotionSet` с повышенным уровнем \(по одному свойству с повышенным уровнем на каждый столбец\).Ключом для этого значения `PromotionSet` является кортеж `InstanceId, PromotionName`.В этом образце в конфигурации был определен один объект `PromotionSet`, атрибутом имени которого является `CounterService`.Обратите внимание на то, что значение столбца `PromotionName` равно атрибуту имени элемента `PromotionSet`.  
  
 Порядок элементов `promotedValue` коррелирует с размещением свойств с повышенным уровнем в представлении `InstancePromotedProperties`.`Count` — первый элемент `promotedValue`.В результате он сопоставляется со столбцом `Value1` в представлении `InstancePromotedProperties`.`LastIncrementedAt` — второй элемент `promotedValue`.В результате он сопоставляется со столбцом `Value2` в представлении `InstancePromotedProperties`.  
  
#### Использование действия PromoteValue  
 Изучите файл CounterService.xamlx в конструкторе [!INCLUDE[wf2](../../../../includes/wf2-md.md)].Обратите внимание, что в определении WF имеются два специальных действия — `PromoteValue<DateTime>` и `PromoteValue<Int32>`.  
  
 В действии `PromoteValue<Int32>` член `Name` определен как `Count`.Этот объект согласуется с первым элементом `promotedValue` в конфигурации и имеет свое значение `Value`, определенное как переменная рабочего процесса `Counter`.При сохранении этого рабочего процесса переменная рабочего процесса `Counter` сохраняется как свойство с повышенным уровнем в столбце `Value1` представления `InstancePromotedProperties`.  
  
 В действии `PromoteValue<DateTime>` член `Name` определен как `LastIncrementedAt`.Этот объект согласуется со вторым элементом `promotedValue` в конфигурации и имеет свое значение `Value`, определенное как переменная рабочего процесса `TimeLastIncremented`.Это означает, что при сохранении этого рабочего процесса переменная рабочего процесса `TimeLastIncremented` сохраняется как свойство с повышенным уровнем в столбце `Value2` представления `InstancePromotedProperties`.  
  
 Следует отметить, что в действии `PromotedValue` имеется также член типа Boolean с именем `ClearExistingPromotedData`.Если этот член задан равным `true`, происходит очистка всех значений свойств с повышенным уровнем вплоть до этой точки в рабочем процессе.Например, допустим, что действие Sequence определено последовательно:  
  
1.  PromoteValue { Name \= "Count", Value \= 3}  
  
2.  PromoteValue {Name \= "LastIncrementedAt", Value \= 1\-1\-2000 }  
  
3.  Persist  
  
4.  PromoteValue {Name \= "Count", Value \= 4, ClearExistingPromotedData \= true}  
  
5.  Persist  
  
 При втором сохранении значением с повышенным уровнем для `Count` будет 4.Но значением с повышенным уровнем для `LastIncrementedAt` будет `NULL`.Если `ClearExistingPromotedData` не задано равным `true` для шага 4, то после второго сохранения значением с повышенным уровнем для Count будет 4.В результате значение с повышенным уровнем для `LastIncrementedAt` все еще останется равным 1\-1\-2000.  
  
### PropertyPromotionActivity  
 Эта библиотека классов содержит следующие общедоступные классы, позволяющие упростить использование средства повышения уровня <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>.  
  
#### Класс PromoteValue  
 Этот класс повышает уровень одного свойства.Имя свойства с повышенным уровнем должно соответствовать атрибуту name элемента `promotedValue` в конфигурации.Это действие может использоваться в конструкторе рабочих процессов.Пример использования см. в описании CounterServiceApplication.  
  
```csharp  
public class PromoteValue<T> : CodeActivity  
{  
    public PromoteValue()  
    {  
    }  
  
    public bool ClearExistingPromotedData { get; set; }  
    public string Name { get; set; }  
    public InArgument<T> Value { get; set; }  
}  
  
```  
  
 ClearExistingPromotedData \(Bool\)  
 Очищает все значения, уровень которых был повышен перед этим действием.  
  
 Name \(string\)  
 Имя, которое представляет данное свойство.Оно должно соответствовать атрибуту name элемента \<promotedValue\> в конфигурации.  
  
 Value \(InArgument\<T\>\)  
 Переменная и\/или значение, которое необходимо сохранить в столбце.  
  
#### Класс PromoteValues  
 Повышает уровень нескольких свойств.Имена свойств с повышенным уровнем должны соответствовать всем атрибутам name в элементах `promotedValue` в конфигурации.Применение аналогично применению в действии `PromoteValue`, за исключением того факта, что повышение уровня нескольких свойств может происходить одновременно.Это действие не может использоваться в конструкторе рабочих процессов.  
  
```  
public class PromoteValues : CodeActivity  
{  
    public PromoteValues()  
    {  
        this.ValuesToPromote = new Dictionary<string, InArgument>();  
    }  
  
    public bool ClearExistingPromotedData { get; set; }  
    public IDictionary<string, InArgument> ValuesToPromote { get; set; }  
}  
```  
  
#### SqlWorkflowInstanceStorePromotionBehavior  
 Происходит от `SqlWorkflowInstanceStoreBehavior`.Этот производный класс добавляет участника настраиваемой сохраняемости \(также в составе этой библиотеки\) как расширение рабочего процесса.Реализация двух предыдущих действий рабочего процесса основана на этом участнике настраиваемой сохраняемости.  
  
```  
public class SqlWorkflowInstanceStorePromotionBehavior :  
             SqlWorkflowInstanceStoreBehavior, IServiceBehavior  
{  
        public void Promote(string name, IEnumerable<string> promoteAsSqlVariant,  
                            IEnumerable<string> promoteAsBinary)  
  
}  
  
```  
  
 Эта библиотека классов содержит также реализацию `ConfigurationElement` для `SqlWorkflowInstanceStorePromotionElement` и участника настраиваемой сохраняемости, используемого предыдущими действиями по повышению уровня.  
  
### PropertyPromotionActivitySQLSample  
 Этот файл SQL создает представление `[dbo].[CounterService]` в дополнение к представлению `[InstancePromotedProperties]` для формирования запросов ко всем экземплярам, в которых задано повышение уровня CounterService.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением работы проверьте наличие следующего \(предусмотренного по умолчанию\) каталога:  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец находится в следующем каталоге:  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Basic\Persistence\PropertyPromotionActivity`  
  
## См. также  
 [Образцы размещения и сохраняемости AppFabric](http://go.microsoft.com/fwlink/?LinkId=193961)