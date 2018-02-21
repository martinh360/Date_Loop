# Date_Loop
        public void Requirement_Run(string startDate)
        {
            string _wcDate = startDate;

            DB_SQL_Connection connectionObject;

            var stopWatchParallel = Stopwatch.StartNew();

            try
            {
                Console.WriteLine("Connection Open ! ");
                connectionObject = new DB_SQL_Connection();
                DB_SQL_Connection newConnection = new DB_SQL_Connection();
                // Clear Staff Groups table
                newConnection.ExecuteQuery("ZeroStaffNeed");

                DateTime wcDate = Convert.ToDateTime(_wcDate);
                Console.WriteLine("Week Commencing Date: " + wcDate);
                DateTime start_Date = wcDate;
                DateTime endDate = start_Date.AddDays(0);

                for (DateTime nDate = start_Date; nDate <= endDate; nDate = start_Date.AddDays(1))
