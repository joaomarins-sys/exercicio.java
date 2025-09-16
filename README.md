package musica;

public abstract class Animal {
    private String nome;
    private String som;

    public Animal(String nome, String som) {
        this.nome = nome;
        this.som = som;
    }

    public String getNome() {
        return nome;
    }

    public String getSom() {
        return som;
    }

    public abstract void cantar();
    public abstract void cantarSom();
}

package musica;

public class Pintinho extends Animal {

    public Pintinho() {
        super("pintinho", "piu");
    }

    @Override
    public void cantar() {
        System.out.println("Lá em casa tinha um " + getNome());
        System.out.println("Lá em casa tinha um " + getNome());
        for (int i = 0; i < 6; i++) {
            cantarSom();
        }
    }

    @Override
    public void cantarSom() {
        System.out.println("E o " + getNome() + " " + getSom());
    }
}

package musica;

public class Galo extends Animal {
    private Animal anterior;

    public Galo(Animal anterior) {
        super("galo", "cocoricó");
        this.anterior = anterior;
    }

    @Override
    public void cantar() {
        System.out.println("Lá em casa tinha um " + getNome());
        System.out.println("Lá em casa tinha um " + getNome());
        cantarSom();
        for (int i = 0; i < 5; i++) {
            anterior.cantarSom();
        }
    }

    @Override
    public void cantarSom() {
        System.out.println("E o " + getNome() + " " + getSom());
    }
}
o
package musica;

public class Galinha extends Animal {
    private Animal anterior;

    public Galinha(Animal anterior) {
        super("galinha", "có");
        this.anterior = anterior;
    }

    @Override
    public void cantar() {
        System.out.println("Lá em casa tinha uma " + getNome());
        System.out.println("Lá em casa tinha uma " + getNome());
        cantarSom();
        anterior.cantar();
    }

    @Override
    public void cantarSom() {
        System.out.println("E a " + getNome() + " " + getSom());
    }
}

package musica;

public class Cachorro extends Animal {
    private Animal anterior;

    public Cachorro(Animal anterior) {
        super("cachorro", "auau");
        this.anterior = anterior;
    }

    @Override
    public void cantar() {
        System.out.println("Lá em casa tinha um " + getNome());
        System.out.println("Lá em casa tinha um " + getNome());
        cantarSom();
        anterior.cantar();
    }

    @Override
    public void cantarSom() {
        System.out.println("E o " + getNome() + " " + getSom());
    }
}

package musica;

public class Gato extends Animal {
    private Animal anterior;

    public Gato(Animal anterior) {
        super("gato", "miau");
        this.anterior = anterior;
    }

    @Override
    public void cantar() {
        System.out.println("Lá em casa tinha um " + getNome());
        System.out.println("Lá em casa tinha um " + getNome());
        cantarSom();
        anterior.cantar();
    }

    @Override
    public void cantarSom() {
        System.out.println("E o " + getNome() + " " + getSom());
    }
}

package musica;

public class Main {
    public static void main(String[] args) {
        Animal pintinho = new Pintinho();
        Animal galo = new Galo(pintinho);
        Animal galinha = new Galinha(galo);
        Animal cachorro = new Cachorro(galinha);
        Animal gato = new Gato(cachorro);

        System.out.println();
        pintinho.cantar();
        System.out.println();
        galo.cantar();
        System.out.println();
        galinha.cantar();
        System.out.println();
        cachorro.cantar();
        System.out.println();
        gato.cantar();
    }
}
