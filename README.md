# using System;
using System.Collections.Generic;
using System.Text;

namespace Financeira
{
    class Contrato
    {
        public int Id { get; set; }
        public string Contratante { get; set; }
        public double Valor { get; set; }
        public int Prazo { get; set; }

        public Contrato()
        {

        }

        public Contrato(int id, string contratante, double valor, int prazo)
        {
            Id = id;
            Contratante = contratante;
            Valor = valor;
            Prazo = prazo;

        }
        public virtual string Contratosla(double calcu)
        {
            return Id
                 + ','
                 + Contratante
                 + ','
                 + Valor
                 + ','
                 + Prazo;
                
        }


    }
}





using System;
using System.Collections.Generic;
using System.Text;

namespace Financeira
{
    class ContratoPessoaFisica : Contrato
    {
        public int CPF { get; set; }
        public int Idade { get; set; }

        public ContratoPessoaFisica()
        {

        }
        
        public ContratoPessoaFisica(int cpf, int idade, int id, string contratante, double valor, int prazo) 
            :  base (id, contratante, valor, prazo)
        {
            CPF = cpf;
            Idade = idade;
        }
        

        public void calcuIfElse(double calcu)
        {
            if (Idade <= 30)
            {
                calcu = Valor + 1;
            }
            else if(Idade <= 40)
            {
                calcu = Valor + 2;
            }
            else if(Idade <= 50)
            {
                calcu = Valor + 3;
            }
            else
            {
                calcu = Valor + 4;
            }
        }

        public override string Contratosla(double calcu)
        {
            return CPF
                + ','
                + Idade
                + ","
                + calcu;
        }
    }
}




using System;
using System.Collections.Generic;
using System.Text;

namespace Financeira
{
    class ContratoPessoaJuridica : Contrato
    {
        public int CNPJ { get; set; }
        public int InscricaoEstadual { get; set; }

        public ContratoPessoaJuridica()
        {

        }

        public ContratoPessoaJuridica(int cnpj, int inscricaoEstadual)
        {
            CNPJ = cnpj;
            InscricaoEstadual = inscricaoEstadual;
        }

        public override string Contratosla()
        {

        }
    }
}
