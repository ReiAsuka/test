even love zzzzzzzzzasdasdss s

	private String XB906(int transNo, String regKey, String param) {
		Map<String,Object> result=new HashMap<String,Object>();
		Gson gson=new Gson();
		int taskId = 0;
		try {
			Map<String,Object> a = gson.fromJson(param, new TypeToken<Map<String,Object>>(){}.getType());
			taskId = (int)(double)(Double)a.get("TASKID");
			IWebServiceData iData = Factory.createInstance();
			return iData.sendData(0xB906,transNo,param);
		} catch (Exception e) {
			this.ERRORCODE=1;
			CommonFunction.WriteExceptionLog(this.LOGPATH, e);
			e.printStackTrace();
		}
		result.put("ERRORCODE", this.ERRORCODE);
		result.put("TASKID", taskId);
		result.put("SEQNO", transNo);
		return gson.toJson(result);
	}
