```scala 
object MarinaCavalari extends Developer {

  override def name: String = "Marina Cavalari"
  override def description: String = "Functional "
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

