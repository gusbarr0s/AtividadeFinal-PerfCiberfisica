import java.util.concurrent.*;

public class CorridaSemControle {

    static int count = 0;

    public static void main(String[] args) throws Exception {
        int T = 8;
        int M = 250_000;

        ExecutorService pool = Executors.newFixedThreadPool(T);

        Runnable r = () -> {
            for (int i = 0; i < M; i++) {
                count++; // condicao de corridar
            }
        };

        long t0 = System.nanoTime();

        for (int i = 0; i < T; i++) {
            pool.submit(r);
        }

        pool.shutdown();
        pool.awaitTermination(1, TimeUnit.MINUTES);

        long t1 = System.nanoTime();
        double tempo = (t1 - t0) / 1e9;

        System.out.printf("Esperado=%d, Obtido=%d, Tempo=%.3fs%n",
                T * M, count, tempo);
    }
}
