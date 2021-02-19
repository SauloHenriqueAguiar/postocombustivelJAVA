# postocombustivelJAVA

/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package com.mycompany.bombadecombustivel;

/**
 *
 * @author Windows
 */
public class BombaDeCombustivel {
 
    private String combustivel;
    private float precoLitro;
    private float qtdLitro;
    private float valorTotal;
    private boolean emAbastecimento;

    public BombaDeCombustivel(String combustivel, float precoLitro) {
        this.combustivel = combustivel;
        this.precoLitro = precoLitro;
        this.qtdLitro = 0f;
        this.valorTotal = 0f;
        this.emAbastecimento = false;
    }
    
    public void puxarGancho(){
        this.emAbastecimento = true;
        this.valorTotal = 0.0f;
        this.qtdLitro = 0.0f;        
        System.out.println(" Bomba " + this.combustivel + "Pronta para abastecer ");
        
    }
    public void voltarGancho(){
        this.emAbastecimento = false;
       System.out.println(" Bomba " + this.combustivel + " parada"); 
       System.out.println("----------------------------------");
       System.out.println("|           POSTO SAULÃO- Recibo         |");
       System.out.println("----------------------------------");
       System.out.println("| Combustivel: |" + this.combustivel );      
       System.out.println("| Preço Litro R$: |" + this.precoLitro );
      System.out.println("| Litros: |" + this.qtdLitro );
      System.out.println("| Valor TOtal: |" + this.valorTotal );
      System.out.println("----------------------------------");
       
    }
    public void abastecerPorLitros(float litros){
        if(this.emAbastecimento){
        this.qtdLitro = litros;
        this.valorTotal  = this.qtdLitro*this.precoLitro;
        System.out.println("Bomba" +this.combustivel + " em abastecimento");
        }
        else{
            System.out.println("Tire a torneira do gancho!");
        }
    }
    public void abastecerPorValor(float valor){
        if(this.emAbastecimento){
            this.valorTotal = valor;
            this.qtdLitro = this.valorTotal/this.precoLitro;
            System.out.println("Bomba" +this.combustivel + " em abastecimento");
        }else{
            System.out.println("Tire a torneira do gancho!");
        }
        
        
    
    }
}
