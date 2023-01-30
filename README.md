# Job-assignment
import java.util.Arrays;
import java.util.Comparator;

public class Jobs {
public static int[] findJobs(int[][] jobs) {
int n = jobs.length;
// Sort the jobs in decreasing order of their profit values
Arrays.sort(jobs, new Comparator<int[]>() {
public int compare(int[] a, int[] b) {
return b[2] - a[2];
}
});
// Initialize the end time of the previously selected job as -1
int end_time = -1;
// Initialize the count of selected jobs as 0
int selected_jobs = 0;
// Initialize the total profit as 0
int total_profit = 0;
for (int[] job : jobs) {
int start_time = job[0];
int end_time1 = job[1];
int profit = job[2];
// Check if it's feasible to perform the job
if (start_time >= end_time) {
selected_jobs++;
total_profit += profit;
end_time1 += end_time1;
}
}
return new int[] {n - selected_jobs, total_profit};
}
public static void main(String[] args) {
int[][] jobs = {{900, 1030, 100}, {1000,1200,500}, {1100,1200,300}};
int[] result = findJobs(jobs);
System.out.println("Number of jobs left: " + result[0]);
System.out.println("Total earnings of other employees: " + result[1]);
int[][] jobs1 = {{900, 1000, 250}, {945,1200,550}, {1130,500,150}};
int[] result1 = findJobs(jobs1);
System.out.println("Number of jobs left: " + result1[0]);
System.out.println("Total earnings of other employees: " + result1[1]);
int[][] jobs2 = {{900, 1030, 100}, {1000,1200,100}, {1100,1200,100}};
int[] result2 = findJobs(jobs2);
System.out.println("Number of jobs left: " + result2[0]);
System.out.println("Total earnings of other employees: " + result2[1]);
}
}
