# Exercicios em POO

![Untitled](Exercicios%20em%20POO%20d81559ef455a4209bf3da372d914245f/Untitled.png)

Solução

```csharp
namespace Exercicios {
    internal class Program {
        static void Main(string[] args) {
           

            Pessoas x , y;
            x = new Pessoas();
            y = new Pessoas();

            Console.WriteLine("dados da primeira pessoa: ");
            x.Nome = Console.ReadLine();
            x.idade= byte.Parse(Console.ReadLine());
            Console.WriteLine("dados da segunda pessoa: ");
            y.Nome = Console.ReadLine();
            y.idade= byte.Parse(Console.ReadLine());

            if(x.idade > y.idade) {
                Console.WriteLine($"Pessoa mais velha {x.Nome}");
            } else {
                Console.WriteLine($"Pessoa mais velha {y.Nome}");
            }
        }
    }
}
```

classe

```csharp
using System;

namespace Exercicios {
    internal class Pessoas {

        public string Nome;
        public byte idade;
        
    }
}
```

![Untitled](Exercicios%20em%20POO%20d81559ef455a4209bf3da372d914245f/Untitled%201.png)

solução

```csharp
using System.Globalization;

namespace Exercicios {
    internal class Program {
        static void Main(string[] args) {

            Funcionarios x, y;
            x = new Funcionarios();
            y = new Funcionarios();

            Console.WriteLine("Dados do primeiro funcionario: ");
            Console.Write("Nome : ");
            x.Nome = Console.ReadLine();
            Console.Write("Salario : ");
            x.salario = double.Parse(Console.ReadLine(),CultureInfo.InvariantCulture);

            Console.WriteLine("Dados do segundo funcionario: ");
            Console.Write("Nome : ");
            y.Nome = Console.ReadLine();
            Console.Write("Salario : ");
            y.salario = double.Parse(Console.ReadLine(),CultureInfo.InvariantCulture);

            double salarioMedio = (y.salario + x.salario)/2;
            Console.WriteLine("Salario medio : " + salarioMedio.ToString("F2",CultureInfo.InvariantCulture));
        }
    }
}
```

Classe

```csharp
	using System;

namespace Exercicios {
    internal class Funcionarios {

        public string Nome;
        public double salario;
        
    }
}
```

![Untitled](Exercicios%20em%20POO%20d81559ef455a4209bf3da372d914245f/Untitled%202.png)

Codigo principal

```csharp
using PrimeiroProjeto;
using System;
using System.Globalization;

internal class Program {
    private static void Main(string[] args) {

        Retangulo x;
        x = new Retangulo();
        
        Console.WriteLine("Entre com a largura e altura do retangulo: ");
        x.largura = double.Parse(Console.ReadLine(),CultureInfo.InvariantCulture);
        x.altura = double.Parse(Console.ReadLine(),CultureInfo.InvariantCulture);

        Console.WriteLine(x);
    }
}
```

Classe:

```csharp
using System;
using System.Globalization;
namespace PrimeiroProjeto {
    internal class Retangulo {

        public double largura;
        public double altura;

        public double Area(){

            return largura * altura;
            }
        public double Perimetro() {

            return (largura + altura)*2.0;
        }
        public double Diagonal() {

            return Math.Sqrt(Math.Pow(largura, 2.0)+Math.Pow(altura, 2.0)); 
        }

        public override string ToString() {
            return "\nAREA = "
                   +Area().ToString("F2", CultureInfo.InvariantCulture)
                   +"\nPERIMETRO = "
                   +Perimetro().ToString("F2", CultureInfo.InvariantCulture)
                   +"\nDIAGONAL = "
                   +Diagonal().ToString("F2",CultureInfo.InvariantCulture);
        }
    }
}
```

![Untitled](Exercicios%20em%20POO%20d81559ef455a4209bf3da372d914245f/Untitled%203.png)

Codigo principal: 

```csharp
using PrimeiroProjeto;
using System;
using System.Globalization;
using System.Security.Cryptography.X509Certificates;

internal class Program {
    private static void Main(string[] args) {

        Funcionarios func = new Funcionarios(); 
        

        Console.Write("Nome: ");
        func.Nome = Console.ReadLine();
        Console.Write("Salario Bruto: ");
        func.SalarioBruto = double.Parse(Console.ReadLine(),CultureInfo.InvariantCulture);
        Console.Write("Imposto: ");
        func.Imposto = double.Parse(Console.ReadLine(), CultureInfo.InvariantCulture);
        Console.WriteLine();

        Console.WriteLine("Funcionário: " + func);

        Console.WriteLine();
        Console.WriteLine("Digite a porcentagem para aumentar o salário: ");
        double porcent = double.Parse(Console.ReadLine(),CultureInfo.InvariantCulture);
        func.AumentarSalario(porcent);

        Console.WriteLine("Dados atualizados: " + func);
    }  
}

```

Classe:

```csharp
using System;
using System.Globalization;
namespace PrimeiroProjeto {
    internal class Funcionarios {

        public String Nome;
        public double SalarioBruto;
        public double Imposto;

        public double SalarioLiquido() {
            return SalarioBruto - Imposto;
            
        }

        public void AumentarSalario(double porcetagem) {
                
              SalarioBruto+=(SalarioBruto * porcetagem /100);
              
        }
        public override string ToString() {
            return  Nome
                   +", $ "
                   +SalarioLiquido().ToString("F2", CultureInfo.InvariantCulture);
        }
    }
}
```

![Untitled](Exercicios%20em%20POO%20d81559ef455a4209bf3da372d914245f/Untitled%204.png)

codigo principal

```sql
using PrimeiroProjeto;
using System;
using System.Globalization;

internal class Program {
     static void Main(string[] args) {

        ConversorDeMoedas dados = new ConversorDeMoedas();

        Console.Write("Qual é a cotação do dolar ? ");
        ConversorDeMoedas.cotacao = double.Parse(Console.ReadLine(),CultureInfo.InvariantCulture);
        Console.Write("Quantos dolares você vai comprar ? ");
        ConversorDeMoedas.dolar = double.Parse(Console.ReadLine(),CultureInfo.InvariantCulture);
        Console.Write(dados);
    }

    
}
```

classe converso de moedas 

```sql
using System;
using System.Globalization;
namespace PrimeiroProjeto {
    internal class ConversorDeMoedas {

        public static double cotacao;
        public static double dolar;

        public static double Calculo() {
             return cotacao * dolar +(cotacao * dolar *6/100);
        }

        public override string ToString() {
            return "Valor a ser pago em reais "
                    +Calculo().ToString("F2",CultureInfo.InvariantCulture);
        }
    }
}
```

O código já está em C#. A única melhoria que posso sugerir é usar variáveis locais em vez de variáveis estáticas na classe `ConversorDeMoedas`. Aqui está o código atualizado:

```csharp
using System;
using System.Globalization;

namespace PrimeiroProjeto
{
    internal class Program
    {
        static void Main(string[] args)
        {
            ConversorDeMoedas dados = new ConversorDeMoedas();

            Console.Write("Qual é a cotação do dólar? ");
            double cotacao = double.Parse(Console.ReadLine(), CultureInfo.InvariantCulture);

            Console.Write("Quantos dólares você vai comprar? ");
            double dolar = double.Parse(Console.ReadLine(), CultureInfo.InvariantCulture);

            Console.Write(dados.Calculo(dolar, cotacao));
        }
    }

    internal class ConversorDeMoedas
    {
        private const double Imposto = 0.06;

        public string Calculo(double dolar, double cotacao)
        {
            double totalEmReais = cotacao * dolar * (1 + Imposto);
            return $"Valor a ser pago em reais: {totalEmReais.ToString("F2", CultureInfo.InvariantCulture)}";
        }
    }
}

```

Nessa versão, usei variáveis locais para armazenar a cotação e a quantidade de dólares que o usuário deseja comprar, em vez de armazená-las em variáveis estáticas na classe `ConversorDeMoedas`. Além disso, movi a lógica do cálculo para um método de instância em vez de um método estático. Também incluí uma constante para o imposto em vez de usar um valor mágico no cálculo.

![Untitled](Exercicios%20em%20POO%20d81559ef455a4209bf3da372d914245f/Untitled%205.png)

![Untitled](Exercicios%20em%20POO%20d81559ef455a4209bf3da372d914245f/Untitled%206.png)

Código Principal:

```csharp
using System.Globalization;
namespace Course {
    class Produto1 {
        static void Main(string[] args) {

            Produto p = new Produto();

            Console.Write("Entre com numero da conta:");
            p.Conta = int.Parse(Console.ReadLine());
            Console.Write("Entre com o nome do titular:");
            p.Nome = Console.ReadLine();
            Console.Write("Haverá depósito inicial (s/n)?");
            p.Desicao = Console.ReadLine();
            if (p.Desicao=="s") {
                Console.Write("Entre o valor de depósito inicial: ");
                p.Deposito = decimal.Parse(Console.ReadLine());
                Console.WriteLine();
            }
            Console.WriteLine("Dados da conta:");
            Console.WriteLine(p);
            Console.WriteLine();

            Console.Write("Entre um valor para depósito:  ");
            decimal dep = decimal.Parse(Console.ReadLine());
            p.depositou(dep);
            Console.WriteLine("Dados da conta atualizados:");
            Console.Write(p);
            Console.WriteLine();

            Console.Write("Entre um valor para saque: ");
            decimal dinheiro = decimal.Parse(Console.ReadLine());
            p.sacou(dinheiro);
            Console.WriteLine(p);

        }
    }
}
```

Classe:

```csharp
using System.Globalization;
namespace Course {
    class Produto {

        public string Nome { private get; set; }
        public int Conta { private get;  set; }
        public decimal Deposito { private get;  set;}
        public decimal Saque { private get;  set; }
        

        public string Desicao;

        public decimal Saldo() {
            return Deposito;
        }
        public void sacou(decimal dinheiro) {
            Deposito-=dinheiro-5.0m;
        }
        public void depositou(decimal deposito) {
            Deposito+=deposito;
        }

        public override string ToString() {
            return "Conta "
                    +Conta
                    +", titular: "
                    +Nome
                    +", Saldo: $ "
                    +Saldo().ToString("F2", CultureInfo.InvariantCulture);
        }
    }
}
```

# Solução de problema com array e POO

```csharp
using System.Globalization;
using System.Runtime.CompilerServices;

namespace Course {
    class Produto1 {
        static void Main(string[] args) {

            Console.Write("Quantos quartos serão alugados ? ");
            int alugados = int.Parse(Console.ReadLine());
            Console.WriteLine();
            Estudante[] aluguel = new Estudante[10];

            for (int i=1; i<=alugados;i++) {

                Console.WriteLine("Aluguel #" + i);
                Console.Write("Nome: ");
                string nome = Console.ReadLine();
                Console.Write("Email: ");
                string email = Console.ReadLine();
                Console.Write("Quarto: ");
                int quarto = int.Parse(Console.ReadLine());
                aluguel[quarto] = new Estudante { Nome = nome, Email = email, Quarto = quarto };
            }

            Console.WriteLine("Quartos ocupados: ");

            for (int i=0;i<=9; i++) {

                
                if (aluguel[i]!=null) {
                    Console.WriteLine(aluguel[i]);
                }

            }
        }
    }
}
```

Classe 

```csharp
namespace Course {
    class Estudante {

      public String Nome { get; set; }
      public String Email { get; set;}
      public int Quarto { get; set; }

        public override string ToString() {
            return Quarto
                   +": "
                   +Nome
                   +", "
                   +Email;
        }
    }
}
```