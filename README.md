# Project Setup Guide For Windows

## 1. Uninstall Existing Java Version
- Open **Control Panel** → **Programs and Features**  
- Uninstall any existing Java version  

## 2. Install Java 1.8
- Download and install **Java 1.8 (JDK 8)** from this github repo.  
- After installation, verify the installed version by running:
  ```sh
  java -version
  ```
  Ensure the output displays **Java 1.8_xx**.

## 3. Verify or Install Maven

### Check Maven Installation
Run the following command in the terminal:
```sh
mvn -version
```
If Maven is not installed, follow these steps:

### Install Maven
1. Download the latest **binary ZIP** from [Maven's official website](https://maven.apache.org/download.cgi).
2. Extract the ZIP file in **C:\ drive**.
3. Copy the path of the `bin` folder inside the extracted directory.
4. Add this path to the **System PATH** variable:
   - Open **Environment Variables** → **System Variables**
   - Find and edit the `Path` variable
   - Add the copied **bin** folder path
5. Create a new system variable:
   - **Variable Name**: `MAVEN_HOME`
   - **Variable Value**: Path to the extracted Maven folder (excluding `bin`)
6. Verify the installation by running:
   ```sh
   mvn -version
   ```

## 4. Open the Project in IntelliJ IDEA

## 5. Install ConQAT Dependency
In the **IDE terminal**, run:
```sh
mvn install:install-file -Dfile="conqat-2017.4.14.jar" -DgroupId=org.conqat -DartifactId=conqat-engine -Dversion=2017.4.14 -Dpackaging=jar
```
This will sync all dependencies.

## 6. Update PostgreSQL Credentials
Ensure that the **PostgreSQL credentials** are correctly set in the following configuration files:
- `src/main/java/config/PostgresConfiguration.java` (inside **IndexBuilder** and **Detector** folders)

---

