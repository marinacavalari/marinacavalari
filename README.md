```scala 
object MarinaCavalari extends Developer {

  override def name: String = "Marina Cavalari"
  override def description: String = "Functional programming enthusiast and data engineer."
  override def country: Country = Country.Brazil
  override def city: City = City.SaoPaulo
  override def bornAt: LocalDate = LocalDate.parse("1997-01-07")
  override def contact: String = "marina.cavalari.mc@gmail.com"
  override def gender: String = "Woman"
  override def age: Int = 24

  def inputs: Set[String] = Set(
    MarinaCavalari.name
  )

  override def definition(datasets: Map[String, DataFrame]): DataFrame = {
    MarinaCavalari
      .transform(skills)
      .transform(education)
      .transform(interest)
      .transform(language)

    def skills(df: Dataframe): Dataframe = {
      df.withColumn(
        "Stack",
        lit(
          "Python",
          "Scala",
          "Clojure",
          "Spark",
          "SQL",
          "HTML",
          "Power BI",
          "JavaScript"
        )
      ).withColumn("Cloud", lit("AWS", "Google CLoud"))
    }

    def education(df: Dataframe): Dataframe = {
      df.withColumn("Bachelor Degree", lit("Business Management"))
        .withColumn("MBA Degree", lit("Data Engenieering, FIAP"))
    }

    def interest(df: Dataframe): Dataframe = {
      df.withColumn(
        "TechInterest",
        lit("Functional Programming", "Data Acess", "Kafka", "Airflow", "Spark")
      ).withColumn(
        "HouseholdInterest",
        lit("Plants", "Decor", "Crochet", "Tennis")
      )
    }

    def langage(df: Dataframe): Dataframe = {
      df.withColumn("SpokeLanguages", lit("Portuguese", "English"))

    }
  }
}
```
<a href="https://web.facebook.com/tenthousandsyears/"> <img src="https://user-images.githubusercontent.com/46076369/114327463-8a2dbc80-9b0f-11eb-9e59-2c8623f342ab.png" width=80px> </a>
<a href="https://www.linkedin.com/in/marina-cavalari/"> <img src="https://user-images.githubusercontent.com/46076369/114327541-e0026480-9b0f-11eb-8f48-2f4aaac92e95.png" width=80px>
<a href="https://www.instagram.com/st4rdust_/"> <img src="https://user-images.githubusercontent.com/46076369/114327665-5a32e900-9b10-11eb-9bc3-5e94c27af5a4.png" width=80px>
<a href="https://api.whatsapp.com/send?phone=5511952471747"> <img src="https://user-images.githubusercontent.com/46076369/114327730-9c5c2a80-9b10-11eb-8bdd-02139ad3a8bc.png" width=80px>
<a href="marina.cavalari.mc@gmail.com"> <img src="https://user-images.githubusercontent.com/46076369/114327735-9e25ee00-9b10-11eb-9b08-64c0f0fd7c07.png" width=80px>
<a href="https://t.me/st4rdust_x"> <img src="https://user-images.githubusercontent.com/46076369/114327724-97977680-9b10-11eb-83a4-0d9a91714967.png" width=80px>




