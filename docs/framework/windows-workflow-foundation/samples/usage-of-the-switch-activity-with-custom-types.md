---
title: "Использование действия Switch с пользовательскими типами | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 482a48c4-eb83-40c3-a4e2-2f9a8af88b75
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Использование действия Switch с пользовательскими типами
В этом образце описывается способ включения действия <xref:System.Activities.> Statements.Switch`1?qualifyHint=False&autoUpgrade=True для оценки определяемого пользователем сложного типа во время выполнения.В большинстве традиционных процедурных языков программирования инструкция [switch](http://go.microsoft.com/fwlink/?LinkId=180521) выбирает логику выполнения в зависимости от результата вычисления переменной.Обычно оператор `switch` работает с выражением, которое может быть оценено статически.Например, в C\# это означает, что поддерживаются только примитивные типы, такие как <xref:System.Boolean>, <xref:System.Int32>, <xref:System.String> и типы перечисления.  
  
 Для поддержки переключения для пользовательского класса необходимо реализовать логику, которая оценивает значения пользовательского сложного типа во время выполнения.Этот образец демонстрирует, реализацию переключения по пользовательскому сложному типу, называемому `Person`.  
  
-   В пользовательском классе атрибут `Person`, a <xref:System.ComponentModel.TypeConverter> объявлен с именем пользовательского объекта <xref:System.ComponentModel.TypeConverter>.  
  
    ```  
    [TypeConverter(typeof(PersonConverter))]  
    public class Person  
    {  
       public string Name { get; set; }  
       public int Age { get; set; }  
    ...  
  
    ```  
  
-   В пользовательском классе `Person` переопределены классы <xref:System.Object.Equals%2A> и <xref:System.Object.GetHashCode%2A>.  
  
    ```  
    public override bool Equals(object obj)  
    {  
        Person person = obj as Person;  
  
        if (person != null)  
        {  
            return string.Equals(this.Name, person.Name);  
        }  
  
        return false;  
    }  
  
    public override int GetHashCode()  
    {  
        if (this.Name != null)  
        {  
            return this.Name.GetHashCode();  
        }  
  
        return 0;  
    }  
  
    ```  
  
-   Реализован пользовательский класс <xref:System.ComponentModel.TypeConverter>, который выполняет преобразование экземпляра пользовательского класса в строку, а строки — в экземпляр пользовательского класса.  
  
    ```  
    public class PersonConverter : TypeConverter  
    {  
        public override bool CanConvertFrom(ITypeDescriptorContext context,  
           Type sourceType)  
        {  
            return (sourceType is string);  
        }  
  
        // Overrides the ConvertFrom method of TypeConverter.  
        public override object ConvertFrom(ITypeDescriptorContext context,  
           CultureInfo culture, object value)  
        {  
            if (value == null)  
            {  
                return null;  
            }  
  
            if (value is string)  
            {  
                return new Person  
                {  
                    Name = (string)value  
                };  
            }  
  
            return base.ConvertFrom(context, culture, value);  
        }  
  
        // Overrides the ConvertTo method of TypeConverter.  
        public override object ConvertTo(ITypeDescriptorContext context,  
           CultureInfo culture, object value, Type destinationType)  
        {  
            if (destinationType == typeof(string))  
            {  
                if (value != null)  
                {  
                    return ((Person) value).Name;  
                }  
                else  
                {  
                    return null;  
                }  
            }  
  
            return base.ConvertTo(context, culture, value, destinationType);  
        }  
    }  
    ```  
  
 В этот образец включены следующие файлы.  
  
-   **Person.cs**: определяет класс `Person`.  
  
-   **PersonConverter.cs**: преобразователь типов для класса `Person`.  
  
-   **Sequence.xaml**: рабочий процесс, который выполняет переключения по типу `Person`.  
  
-   **Program.cs**: основная функция, которая запускает рабочий процесс.  
  
#### Использование этого образца  
  
1.  Загрузите Switch.sln в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Чтобы построить решение, нажмите CTRL\+SHIFT\+B.  
  
3.  Чтобы запустить образец, нажмите клавиши CTRL\+F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Switch`  
  
## См. также  
 [Встроенная библиотека действий](../../../../docs/framework/windows-workflow-foundation//net-framework-4-5-built-in-activity-library.md)