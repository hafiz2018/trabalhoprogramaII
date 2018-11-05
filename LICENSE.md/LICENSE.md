1 questao
public class MyTest {
    static int i = 0;
    public static void main(String[] args) {
        new  Thread(t1).start();
        new  Thread(t2).start();
        new Thread(t3).start();
        new Thread(t4).start();
        new Thread(t5).start();


    }
 
    private static void countMe(String name){
        i++;
        System.out.println("Current Counter is: " + i + ", updated by: " + name);
    }
 
    private static Runnable t1 = new Runnable() {
        public void run() {
            try{
                for(int i=0; i<5; i++){
                    countMe("t1");
                }
            } catch (Exception e){}
 
        }
    };
 
    private static Runnable t2 = new Runnable() {
        public void run() {
            try{
                for(int i=0; i<5; i++){
                    countMe("t2");
                }
            } catch (Exception e){}
       }
    };
   private static Runnable t3 = new Runnable() {
        public void run() {
            try{
                for(int i=0; i<5; i++){
                    countMe("t3");
                }
            } catch (Exception e){}
 
        }
    };


   private static Runnable t4 = new Runnable() {
        public void run() {
            try{
                for(int i=0; i<5; i++){
                    countMe("t4");
                }
            } catch (Exception e){}
 
        }
    };
   private static Runnable t5 = new Runnable() {
        public void run() {
            try{
                for(int i=0; i<5; i++){
                    countMe("t5");
                }
            } catch (Exception e){}
 
        }
    };
}


 


















2 questao
import java.util.Arrays;
import java.util.Random;
import java.util.Scanner;
public class Matriz_Espelho {
public static void main(String[] args) {
        new  Thread(t1).start();
        new  Thread(t2).start();
        new  Thread(t3).start();
}
public class Matriz {
int linhasMatrizA;
int colunasMatrizA;

    int [][] matrizA;

Scanner entrada = new Scanner(System.in);
System.out.println("Insira o numero de LINHAS da matriz A:");
linhasMatrizA = entrada.nextInt();
System.out.println("Insira o numero de COLUNAS da matriz A:");
colunasMatrizA = entrada.nextInt();
matrizA = new int[linhasMatrizA][colunasMatrizA];

System.out.println("Matriz A e [" + linhasMatrizA + "]" + "[" + colunasMatrizA + "]");
System.out.println("Preenchendo Matriz A");
for(int i = 0; i < matrizA.length; i++){
for (int j = 0; j < matrizA[0].length; j++){
System.out.println("Digite o valor para a posicao [" + i + "]" + "[" + j + "] da matriz A" );
matrizA[i][j] = entrada.nextInt();
}
}
System.out.println();
System.out.println("Matriz Pincipal: ");
for (int i = 0; i < matrizA.length; i++) {
for (int j = 0; j < matrizA.length; j++) {
System.out.printf(" %d ", matrizA[i][j]);
}
System.out.println();
}
System.out.println();
System.out.println("Matriz Diagonal: ");
for (int i = 0; i < matrizA.length; i++) {
for (int j = 0; j < matrizA.length; j++) {
System.out.printf(" %d ", matrizA[j][i]);
}
System.out.println();
}
}
private static Runnable t1 = new Runnable() {
        public void run() {
            try{
                int soma = 0;
                for(int j=0; j<5; j++){
                    soma += matrizA[0][j];
                }
            } catch (Exception e){}
 
        }
    };
private static Runnable t1 = new Runnable() {
        public void run() {
            try{
               int soma = 0;
                for(int i=0; i<5; i++){
                    soma += matrizA[1][j];
                }
            } catch (Exception e){}
 
        }
    };
private static Runnable t1 = new Runnable() {
        public void run() {
            try{
                  int soma = 0;
                for(int i=0; i<5; i++){
                    soma += matrizA[2][j];
                }
            } catch (Exception e){}
 
        }
    };
}




3 questao
package controller;







import java.util.Random;


import javax.swing.JLabel;





public class ThreadMaquina extends Thread {


private JLabel n;


private int op;





/**


* Construtor


* @param n é a label que mostrará o número a ser sorteado


* @param op significa qual label iniciará a contagem aleatória após o botão ser acionado 


*/


public ThreadMaquina(JLabel n, int op) {


this.n = n;


this.op = op;


}





/**


* método run que efetua achamada do método executa sem a passagem de parâmetros


*/





@Override


public void run() {


executa();


}





/**


* método executa que contém um switch case para analisar op e repassar os parâmetros


* necessários para o método numero


*/





public void executa() {


switch(op) {


case 0: 


numero(op);


break;


case 1:


numero(op);


break;


case 2:


numero(op);


break;


}


}





/**


* Método número que fara o sorteio aleatório dos números 


* @param op recebe o número da opção do switch case 


* a fim de estipular um limite no for


*/





public void numero(int op) {


int numero;


String num;





Random random = new Random();


int valor_final = (op+1) * 2000000; 





for(int i = 0; i < valor_final; i++) {


numero = random.nextInt(7);


num = ""+numero;


n.setText(num);


}


}


}

89  src/view/Principal.java


@@ -0,0 +1,89 @@


/**


* 





*


*/





package view;



3 questao

import java.awt.Color;


import java.awt.EventQueue;


import java.awt.Font;





import javax.swing.ImageIcon;


import javax.swing.JButton;


import javax.swing.JFrame;


import javax.swing.JLabel;


import javax.swing.JPanel;


import javax.swing.border.EmptyBorder;





import controller.ControlaMaquina;





public class Principal extends JFrame{


private static final long serialVersionUID = 1L;


private JPanel painel;





public static void main(String[] args){


EventQueue.invokeLater(new Runnable() {


public void run() {


try {


Principal frame = new Principal();


frame.setVisible(true);


} catch (Exception e) {


e.printStackTrace();


}


}


});


}





/**


*É o método responsável por construir o JFrame, posicionando suas respectivas Labels e button 


*/





public Principal() {


setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);


setBounds(400, 90, 556, 577);


setResizable(false);





painel = new JPanel();


painel.setBorder(new EmptyBorder(5, 5, 5, 5));





setContentPane(painel);


painel.setLayout(null);





JLabel n1 = new JLabel("0");


n1.setBounds(55, 230, 150, 200);


n1.setFont(new Font ("Calibri", Font.BOLD, 200 ));





painel.add(n1);





JLabel n2 = new JLabel("0");


n2.setBounds(230, 230, 150, 200);


n2.setFont(new Font ("Calibri", Font.BOLD, 200 ));





painel.add(n2);





JLabel n3 = new JLabel("0");


n3.setBounds(405, 230, 150, 200);


n3.setFont(new Font ("Calibri", Font.BOLD, 200 ));





painel.add(n3);





JLabel fundo = new JLabel("");


fundo.setBounds(0 , 0, 550, 550);


fundo.setIcon(new ImageIcon("imagens/fundo_caca_niquel.png"));





painel.add(fundo);





JButton btnJogar = new JButton("JOGAR");


btnJogar.setBounds(145, 455, 250, 65);


btnJogar.setFont(new Font ("Calibri", Font.BOLD, 50 ));


btnJogar.setBackground(Color.WHITE);





painel.add(btnJogar);





ControlaMaquina cm = new ControlaMaquina(n1, n2, n3);


btnJogar.addActionListener(cm);


}





}


private JediSubscriber sub;




private JSONObject json;


private Jogada jogada;


private static String minhaJogada;


private static String msg;





public JogoDaVelha() {


minhaJogada = "inicio";


sub = new JediSubscriber();


sub.setupSubscriber();


pub = new JediPublisher();

@@ -174,6 +177,7 @@ public void Vencedor(String JogadorVencedor) {


JOptionPane.showMessageDialog(null, "Empate!");


LimparCampos();


}


System.exit(0);


}





public void LimparCampos() {

@@ -195,6 +199,9 @@ public void LimparCampos() {


B8.setEnabled(true);


B9.setText("");


B9.setEnabled(true);


minhaJogada = "novo";


msg = "novo";








Jogador1Ativo = true;


Jogador2Ativo = false;

@@ -563,13 +570,16 @@ private void threadSub() {


Thread t = new Thread(new Runnable() {


@Override


public void run() {


// String msg = "vazio";


while (true) {


String msg = sub.getMsg();


msg = sub.getMsg();


System.out.println(msg);


if (msg != null) {


if (!msg.equals(sub.getMsg())) {


System.out.println(msg);


if (!minhaJogada.equals(msg)) {


System.out.println("jogada diferente");


marcarBotao(msg);


repaint();


}


System.out.println(msg);


}


}


}



View 
37  src/tictactoeswing/TesteComunicação.form

@@ -28,51 +28,32 @@


<Group type="103" groupAlignment="0" attributes="0">


<Group type="102" alignment="0" attributes="0">


<EmptySpace min="-2" pref="20" max="-2" attributes="0"/>


<Group type="103" groupAlignment="0" max="-2" attributes="0">


<Component id="tfRecebido" pref="137" max="32767" attributes="0"/>


<Component id="tfTeste" max="32767" attributes="0"/>


<Group type="103" groupAlignment="0" attributes="0">


<Component id="jLabel1" min="-2" max="-2" attributes="0"/>


<Component id="tfRecebido" min="-2" pref="137" max="-2" attributes="0"/>


</Group>


<EmptySpace type="unrelated" max="-2" attributes="0"/>


<Component id="btnEnviar" min="-2" max="-2" attributes="0"/>


<EmptySpace pref="137" max="32767" attributes="0"/>


<EmptySpace pref="243" max="32767" attributes="0"/>


</Group>


</Group>


</DimensionLayout>


<DimensionLayout dim="1">


<Group type="103" groupAlignment="0" attributes="0">


<Group type="102" alignment="0" attributes="0">


<EmptySpace min="-2" pref="36" max="-2" attributes="0"/>


<Component id="jLabel1" min="-2" max="-2" attributes="0"/>


<EmptySpace max="-2" attributes="0"/>


<Group type="103" groupAlignment="3" attributes="0">


<Component id="tfTeste" alignment="3" min="-2" pref="27" max="-2" attributes="0"/>


<Component id="btnEnviar" alignment="3" min="-2" max="-2" attributes="0"/>


</Group>


<EmptySpace type="separate" max="-2" attributes="0"/>


<Component id="tfRecebido" min="-2" max="-2" attributes="0"/>


<EmptySpace pref="224" max="32767" attributes="0"/>


</Group>


</Group>


</DimensionLayout>


</Layout>


<SubComponents>


<Component class="javax.swing.JTextField" name="tfTeste">


<Properties>


<Property name="text" type="java.lang.String" value="jTextField1"/>


</Properties>


<Events>


<EventHandler event="actionPerformed" listener="java.awt.event.ActionListener" parameters="java.awt.event.ActionEvent" handler="tfTesteActionPerformed"/>


</Events>


</Component>


<Component class="javax.swing.JButton" name="btnEnviar">


<Properties>


<Property name="text" type="java.lang.String" value="jButton1"/>


</Properties>


<Events>


<EventHandler event="actionPerformed" listener="java.awt.event.ActionListener" parameters="java.awt.event.ActionEvent" handler="btnEnviarActionPerformed"/>


</Events>


</Component>


<Component class="javax.swing.JTextField" name="tfRecebido">


</Component>


<Component class="javax.swing.JLabel" name="jLabel1">


<Properties>


<Property name="text" type="java.lang.String" value="jTextField1"/>


<Property name="text" type="java.lang.String" value="C&#xe9;lula Clicada"/>


</Properties>


</Component>


</SubComponents>



View 
50  src/tictactoeswing/TesteComunicação.java

@@ -31,9 +31,8 @@


// <editor-fold defaultstate="collapsed" desc="Generated Code">//GEN-BEGIN:initComponents


private void initComponents() {





tfTeste = new javax.swing.JTextField();


btnEnviar = new javax.swing.JButton();


tfRecebido = new javax.swing.JTextField();


jLabel1 = new javax.swing.JLabel();





setDefaultCloseOperation(javax.swing.WindowConstants.DO_NOTHING_ON_CLOSE);


addWindowListener(new java.awt.event.WindowAdapter() {

@@ -42,60 +41,32 @@ public void windowClosing(java.awt.event.WindowEvent evt) {


}


});





tfTeste.setText("jTextField1");


tfTeste.addActionListener(new java.awt.event.ActionListener() {


public void actionPerformed(java.awt.event.ActionEvent evt) {


tfTesteActionPerformed(evt);


}


});





btnEnviar.setText("jButton1");


btnEnviar.addActionListener(new java.awt.event.ActionListener() {


public void actionPerformed(java.awt.event.ActionEvent evt) {


btnEnviarActionPerformed(evt);


}


});





tfRecebido.setText("jTextField1");


jLabel1.setText("Célula Clicada");





javax.swing.GroupLayout layout = new javax.swing.GroupLayout(getContentPane());


getContentPane().setLayout(layout);


layout.setHorizontalGroup(


layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)


.addGroup(layout.createSequentialGroup()


.addGap(20, 20, 20)


.addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING, false)


.addComponent(tfRecebido, javax.swing.GroupLayout.DEFAULT_SIZE, 137, Short.MAX_VALUE)


.addComponent(tfTeste))


.addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.UNRELATED)


.addComponent(btnEnviar)


.addContainerGap(137, Short.MAX_VALUE))


.addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)


.addComponent(jLabel1)


.addComponent(tfRecebido, javax.swing.GroupLayout.PREFERRED_SIZE, 137, javax.swing.GroupLayout.PREFERRED_SIZE))


.addContainerGap(243, Short.MAX_VALUE))


);


layout.setVerticalGroup(


layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)


.addGroup(layout.createSequentialGroup()


.addContainerGap()


.addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)


.addComponent(tfTeste, javax.swing.GroupLayout.PREFERRED_SIZE, 27, javax.swing.GroupLayout.PREFERRED_SIZE)


.addComponent(btnEnviar))


.addGap(18, 18, 18)


.addGap(36, 36, 36)


.addComponent(jLabel1)


.addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)


.addComponent(tfRecebido, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE)


.addContainerGap(224, Short.MAX_VALUE))


);





pack();


}// </editor-fold>//GEN-END:initComponents





private void tfTesteActionPerformed(java.awt.event.ActionEvent evt) {//GEN-FIRST:event_tfTesteActionPerformed


// TODO add your handling code here:


}//GEN-LAST:event_tfTesteActionPerformed





private void btnEnviarActionPerformed(java.awt.event.ActionEvent evt) {//GEN-FIRST:event_btnEnviarActionPerformed


JediPublisher pub = new JediPublisher();


pub.postar("canal", tfTeste.getText());


tfTeste.setText(null);


}//GEN-LAST:event_btnEnviarActionPerformed





private void formWindowClosing(java.awt.event.WindowEvent evt) {//GEN-FIRST:event_formWindowClosing





System.exit(0);

@@ -158,9 +129,8 @@ public void run() {







4 questao
// Variables declaration - do not modify//GEN-BEGIN:variables


private javax.swing.JButton btnEnviar;


private javax.swing.JLabel jLabel1;


private javax.swing.JTextField tfRecebido;


private javax.swing.JTextField tfTeste;


// End of variables declaration//GEN-END:variables


private JediSubscriber sub;


}


<?xml version="1.0" encoding="UTF-8"?>




<classpath>


<classpathentry kind="src" output="target/classes" path="src/main/java">


<attributes>


<attribute name="optional" value="true"/>


<attribute name="maven.pomderived" value="true"/>


</attributes>


</classpathentry>


<classpathentry excluding="**" kind="src" output="target/classes" path="src/main/resources">


<attributes>


<attribute name="maven.pomderived" value="true"/>


</attributes>


</classpathentry>


<classpathentry kind="src" output="target/test-classes" path="src/test/java">


<attributes>


<attribute name="optional" value="true"/>


<attribute name="maven.pomderived" value="true"/>


</attributes>


</classpathentry>


<classpathentry excluding="**" kind="src" output="target/test-classes" path="src/test/resources">


<attributes>


<attribute name="maven.pomderived" value="true"/>


</attributes>


</classpathentry>


<classpathentry kind="con" path="org.eclipse.jdt.launching.JRE_CONTAINER/org.eclipse.jdt.internal.debug.ui.launcher.StandardVMType/J2SE-1.5">


<attributes>


<attribute name="maven.pomderived" value="true"/>


</attributes>


</classpathentry>


<classpathentry kind="con" path="org.eclipse.m2e.MAVEN2_CLASSPATH_CONTAINER">


<attributes>


<attribute name="maven.pomderived" value="true"/>


</attributes>


</classpathentry>


<classpathentry kind="output" path="target/classes"/>


</classpath>

View 
1  JogoMemoriaSwing/.gitignore


@@ -0,0 +1 @@


/target/

View 
23  JogoMemoriaSwing/.project


@@ -0,0 +1,23 @@


<?xml version="1.0" encoding="UTF-8"?>


<projectDescription>


<name>JogoMemoriaSwing</name>


<comment></comment>


<projects>


</projects>


<buildSpec>


<buildCommand>


<name>org.eclipse.jdt.core.javabuilder</name>


<arguments>


</arguments>


</buildCommand>


<buildCommand>


<name>org.eclipse.m2e.core.maven2Builder</name>


<arguments>


</arguments>


</buildCommand>


</buildSpec>


<natures>


<nature>org.eclipse.jdt.core.javanature</nature>


<nature>org.eclipse.m2e.core.maven2Nature</nature>


</natures>


</projectDescription>

View 
5  JogoMemoriaSwing/.settings/org.eclipse.jdt.core.prefs


@@ -0,0 +1,5 @@


eclipse.preferences.version=1


org.eclipse.jdt.core.compiler.codegen.targetPlatform=1.5


org.eclipse.jdt.core.compiler.compliance=1.5


org.eclipse.jdt.core.compiler.problem.forbiddenReference=warning


org.eclipse.jdt.core.compiler.source=1.5

View 
4  JogoMemoriaSwing/.settings/org.eclipse.m2e.core.prefs


@@ -0,0 +1,4 @@


activeProfiles=


eclipse.preferences.version=1


resolveWorkspaceProjects=true


version=1

View 
34  JogoMemoriaSwing/pom.xml


@@ -0,0 +1,34 @@


<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 


xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">





<modelVersion>4.0.0</modelVersion>


<groupId>com.wordpress.luizgustavoss</groupId>


<artifactId>JogoMemoriaSwing</artifactId>


<version>1.0</version>





<build>


<plugins>


<plugin>


<groupId>org.apache.maven.plugins</groupId>


<artifactId>maven-shade-plugin</artifactId>


<version>3.0.0</version>


<executions>


<execution>


<phase>package</phase>


<goals>


<goal>shade</goal>


</goals>


<configuration>


<transformers>


<transformer implementation="org.apache.maven.plugins.shade.resource.ManifestResourceTransformer">


<mainClass>com.wordpress.luizgustavoss.TelaUm</mainClass>


</transformer>


</transformers>


</configuration>


</execution>


</executions>


</plugin>


</plugins>


</build>





</project> 

View 
34  JogoMemoriaSwing/src/main/java/com/wordpress/luizgustavoss/Jogador.java


@@ -0,0 +1,34 @@


package com.wordpress.luizgustavoss;




5 questao
/**


* Classe que representa o Jogador com seus atributos


* 


*


*/


public class Jogador{





private String nome;


private int pontos;





public Jogador(String nomeJogador){ 


nome = (nomeJogador.equals("")? "Jogador": nomeJogador );


pontos = 0;


}





public String obterNome(){ 


return nome;


}





public int obterPontos(){ 


return pontos;


}





public void incrementarPontos(){ 


pontos += 5;


}





public void decrementarPontos(){ 


pontos--;


}





} 

View 
36  JogoMemoriaSwing/src/main/java/com/wordpress/luizgustavoss/MyButton.java


@@ -0,0 +1,36 @@


package com.wordpress.luizgustavoss;





import javax.swing.*;





/**


* Especialização de um JButton para armazenar dois ícones


* 


* 


*


*/


public class MyButton extends JButton{





private static final long serialVersionUID = 1L;





private Icon imagemPadrao;


private Icon imagemBotao;





public MyButton(Icon imagemPadrao, Icon imagemBotao){


super(); 


this.imagemBotao = imagemBotao;


this.imagemPadrao = imagemPadrao;


setImagemPadrao();


}





public void setImagemPadrao(){ 


this.setIcon(imagemPadrao);


}





public void setImagemBotao(){ 


this.setIcon(imagemBotao);


} 





public Icon getImagemBotao(){ 


return this.imagemBotao;


}


}

View 
335  JogoMemoriaSwing/src/main/java/com/wordpress/luizgustavoss/TelaJogo.java


@@ -0,0 +1,335 @@







import java.awt.*;


import java.awt.event.*;





import javax.swing.*;








/**


* Tela do Jogo


* 


*


*


*/


public class TelaJogo extends JFrame implements ActionListener {





private static final long serialVersionUID = 1L;





private Object botaoClicadoUm, botaoClicadoDois;


private JLabel pontosJogador, labelPontosJogador;


private Icon imagens[], imagens8[];


private Container container;


private String tema;


private Jogador objJogadorJogada;


private int fator, qtdeAcerto, qtdeTentativas;


private boolean primeiroClique = true;


private boolean acertou = true;


private MyButton botaoUm, botaoDois, posicoesFiguras[];








public TelaJogo(Jogador jogador, int codigoJogo, int fatorJogo) {





super("Jogo da Memória");





setLocation(200, 10);





addWindowListener(new WindowAdapter() {


public void windowClosing(WindowEvent windowEvent) {


mostrarResumoJogo();


}


});





inicializarComponentesDeTela(jogador, codigoJogo, fatorJogo);


}











/**


* Inicialização dos componentes de tela


* 


* @param jogador


* @param codigoJogo


* @param fatorJogo


*/


private void inicializarComponentesDeTela(Jogador jogador, int codigoJogo, int fatorJogo) {





fator = fatorJogo;





objJogadorJogada = jogador;


temaJogada(codigoJogo);


preparaArrayImagens();


container = getContentPane();





container.add(configurarPainelPontos(), BorderLayout.NORTH);


container.add(configurarBotaoSair(), BorderLayout.SOUTH);


container.add(configurarPainelImagem());





double d_largura = (fator == 4 ? 82.5 : 80);





d_largura *= fator;





int i_largura = (int) d_largura;





setSize(i_largura, i_largura + 70);


setVisible(true);


setResizable(false);


}











/**


* Prepara o Array de Imagens


*/


private void preparaArrayImagens() {





int posicaoNoArray, x, y;





this.imagens8 = new Icon[(fator * fator) / 2];





for (x = 0; x < ((fator * fator) / 2); x++) {


this.imagens8[x] = new ImageIcon(getClass().getClassLoader().getResource(


tema + (x + 1) + ".png"));


}





this.imagens = new Icon[(fator * fator)];





for (x = 0; x < 2; x++) {


for (y = 0; y < ((fator * fator) / 2); y++) {


do {


posicaoNoArray = (int) (Math.random() * (fator * fator));


} while (this.imagens[posicaoNoArray] != null);





this.imagens[posicaoNoArray] = imagens8[y];


}


}


}











/**


* Descobre o tema escolhido


* 


* @Param codTema - Código do tema escolhido


*/


private void temaJogada(int codigoTema) {





switch (codigoTema) {


case 1:


this.tema = "imagens/temas/superheroes/";


break;


case 2:


this.tema = "imagens/temas/alcoholdrinks/";


break;


}


}








/**


* Mostra o resumo do jogo ao sair


*


*/


private void mostrarResumoJogo() {





StringBuilder resumoJogo = new StringBuilder();


resumoJogo.append("Jogador: ").append(objJogadorJogada.obterNome()).append("\n\n");


resumoJogo.append("Pontos: ").append(objJogadorJogada.obterPontos()).append("\n\n");


resumoJogo.append("Quantidade de tentativas: ").append(qtdeTentativas);





JOptionPane.showMessageDialog(null, resumoJogo.toString(), "Resumo do Jogo",


JOptionPane.INFORMATION_MESSAGE);





setVisible(false);


}








/**


* Configura o botão sair


* 


* @return o botão configurado


*/


private JButton configurarBotaoSair(){





JButton botaoSair = new JButton(" Sair do Jogo ", configurarIconeSair());


botaoSair.setRolloverIcon(configurarIconeSairRoll());


botaoSair.setActionCommand("botaoSair");


botaoSair.addActionListener(this);





return botaoSair;


}











/**


* Configurando o painel superior


* 


* @return o painel configurado


*/


private JPanel configurarPainelPontos(){





labelPontosJogador = new JLabel("Jogador: " + objJogadorJogada.obterNome() + " | Pontos: ");





pontosJogador = new JLabel(String.valueOf(objJogadorJogada.obterPontos()));





JPanel painelPontos = new JPanel();





painelPontos.setBackground(Color.white);


painelPontos.add(labelPontosJogador);


painelPontos.add(pontosJogador);





return painelPontos;


}








/**


* Configura o painel de imagem


* 


* @return o painel configurado


*/


private JPanel configurarPainelImagem(){





JPanel painelImagens = new JPanel(); 


GridLayout grid = new GridLayout(fator, fator, 5, 5);


painelImagens.setLayout(grid);





posicoesFiguras = new MyButton[(fator * fator)];





for (int cont = 0; cont < (fator * fator); cont++) {


posicoesFiguras[cont] = new MyButton(configurarIconePadrao(), imagens[cont]);


posicoesFiguras[cont].addActionListener(this);


painelImagens.add(posicoesFiguras[cont]);


}





return painelImagens;


}








/**


* Configura o ícone Padrão


* 


* @return o ícone configurado


*/


private Icon configurarIconePadrao(){


Icon imagemPadrao = new ImageIcon(


getClass().getClassLoader().getResource("imagens/jogo/standard.png"));


return imagemPadrao;


}








/**


* Configura o ícone Sair


* 


* @return o ícone configurado


*/


private Icon configurarIconeSair(){


Icon imagemSair = new ImageIcon(getClass().getClassLoader().getResource(


"imagens/jogo/sair.png"));


return imagemSair;


}








/**


* Configura o ícone SairRoll


* 


* @return o ícone configurado


*/


private Icon configurarIconeSairRoll(){


Icon imagemSairRoll = new ImageIcon(getClass().getClassLoader().getResource(


"imagens/jogo/sairroll.png"));


return imagemSairRoll;


}








/**


* Listener de eventos para os botões


*/


public void actionPerformed(ActionEvent event) {





/*Se o evento for do botão Sair...*/


if ("botaoSair".equals(event.getActionCommand())) {


mostrarResumoJogo();


}





/*Caso contrário é evento de botões de imagem*/


else {





/*testa se é o primeiro clique*/


if (primeiroClique) {





qtdeTentativas++;





/*testa se o jogador errou na jogada anterior*/


if (!acertou) {





botaoUm = (MyButton) botaoClicadoUm;


botaoDois = (MyButton) botaoClicadoDois;





botaoUm.setImagemPadrao();


botaoDois.setImagemPadrao();


}





botaoClicadoUm = event.getSource();





botaoUm = (MyButton) botaoClicadoUm;


botaoUm.setImagemBotao();





/*indica que este foi o primeiro clique*/


primeiroClique = !primeiroClique;


}





/*se não for o primeiro clique*/


else {





botaoClicadoDois = event.getSource();


botaoDois = (MyButton) botaoClicadoDois;





/*verifica se o jogador clicou no mesmo botão*/


if (botaoClicadoDois == botaoClicadoUm) {


acertou = false;


mostrarMensagemDeAcaoNaoPermitida();


} else {





botaoDois.setImagemBotao(); // coloca a imagem no botão





/*compara com o primeiro botão clicado*/


if (botaoUm.getImagemBotao().equals(


botaoDois.getImagemBotao())) {





acertou = true;


qtdeAcerto++;





/*Desabilita os botões*/


botaoUm.setEnabled(false);


botaoDois.setEnabled(false);





/*incrementar pontos*/


objJogadorJogada.incrementarPontos();


pontosJogador.setText(String.valueOf(objJogadorJogada.obterPontos()));





/* se foi o último par encontrado, apresenta 


resumo do jogo e fecha a janela */


if (qtdeAcerto == ((fator * fator) / 2)) {


mostrarResumoJogo();


setVisible(false);


}


} else {


acertou = false; // decrementar pontos


objJogadorJogada.decrementarPontos();


pontosJogador.setText(String.valueOf(objJogadorJogada.obterPontos()));


}


primeiroClique = !primeiroClique; // indica que este foi o segundo clique


}


}


}


}








/**


* Apresenta mensagem de alerta de operação não permitida


*/


private void mostrarMensagemDeAcaoNaoPermitida() {


JOptionPane.showMessageDialog(null, "Ação não permitida!",


"Ação Não Permitida", JOptionPane.WARNING_MESSAGE);


}





} 

